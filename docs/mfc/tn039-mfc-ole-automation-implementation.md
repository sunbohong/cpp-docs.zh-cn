---
description: 了解有关以下内容的详细信息： TN039： MFC/OLE 自动化实现
title: TN039： MFC OLE 自动化实现
ms.date: 06/28/2018
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: caabd3719a467e534e47ca61ed8f9a9f1f0d2eb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215412"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039：MFC/OLE 自动化实现

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch 接口概述

`IDispatch`接口是应用程序公开方法和属性的方法，使其他应用程序（如 VISUAL BASIC 或其他语言）可以利用应用程序的功能。 此接口最重要的部分是 `IDispatch::Invoke` 函数。 MFC 使用 "调度映射" 来实现 `IDispatch::Invoke` 。 调度映射提供有关派生类的布局或 "shape" 的 MFC 实现信息 `CCmdTarget` ，以便它可以直接操作对象的属性，或调用对象中的成员函数来满足 `IDispatch::Invoke` 请求。

大多数情况下，ClassWizard 和 MFC 共同从应用程序程序员中隐藏了 OLE 自动化的大部分细节。 程序员关注要在应用程序中公开的实际功能，无需担心基础管道的问题。

但在某些情况下，有必要了解 MFC 在幕后执行的操作。 此注释将介绍框架如何将 **DISPID** 分配给成员函数和属性。 仅当需要知道 Id （如为应用程序的对象创建 "类型库" 时）时，才需要知道 MFC 用于分配 **DISPID** 的算法。

## <a name="mfc-dispid-assignment"></a>MFC DISPID 赋值

尽管自动化 (Visual Basic 用户（例如) ）的最终用户可查看其代码中启用的自动化属性和方法的实际名称 (例如 obj。ShowWindow) ，的实现 `IDispatch::Invoke` 不会接收实际名称。 出于优化原因，它会接收 **DISPID**，这是一个32位 "幻 cookie"，用于描述要访问的方法或属性。 这些 **DISPID** 值 `IDispatch` 通过调用的另一种方法从实现返回 `IDispatch::GetIDsOfNames` 。 自动化客户端应用程序将 `GetIDsOfNames` 为它打算访问的每个成员或属性调用一次，并将其缓存，以便以后调用 `IDispatch::Invoke` 。 这样一来，开销高昂的字符串查找只对每个对象使用一次，而不是每次调用一次 `IDispatch::Invoke` 。

MFC 根据两项内容确定每个方法和属性的 **DISPID**：

- 从调度映射顶部 (1 相对) 的距离

- 调度映射距派生程度最高的类的距离 (0 相对) 

**DISPID** 分为两部分。 **DISPID** 的 **LOWORD** 包含第一个组件，即与调度映射顶部的距离。 **HIWORD** 包含来自派生程度最高的类的距离。 例如：

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

如您所见，有两个类，两者都公开了 OLE 自动化接口。 其中一个类派生自另一个类，因此利用基类的功能，包括 OLE 自动化部分 ( "x" 和 "y" 属性，这种情况) 。

MFC 将为类 CDispPoint 生成 **DISPID** 的，如下所示：

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

由于属性不在基类中，因此 **DISPID** 的 **HIWORD** 始终为零 (CDispPoint 的派生类的最大距离为) 零。

MFC 将为类 CDisp3DPoint 生成 **DISPID** 的，如下所示：

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

为 Z 属性提供了一个具有零 **HIWORD** 的 **DISPID** ，因为它是在公开属性 CDisp3DPoint 的类中定义的。 由于 X 和 Y 属性是在基类中定义的，因此 **DISPID** 的 **HIWORD** 为1，因为在其中定义这些属性的类是从派生程度最高的类中的一个派生的距离。

> [!NOTE]
> **LOWORD** 始终由地图中的位置确定，即使映射中存在具有显式 **DISPID** 的条目 (参阅下一节，了解有关和宏) 的 **_ID** 版本的信息 `DISP_PROPERTY` `DISP_FUNCTION` 。

## <a name="advanced-mfc-dispatch-map-features"></a>高级 MFC 调度映射功能

在此版本的 Visual C++ 中，ClassWizard 不支持许多其他功能。 ClassWizard 支持 `DISP_FUNCTION` 、 `DISP_PROPERTY` 和， `DISP_PROPERTY_EX` 分别用于定义方法、成员变量属性和 get/set 成员函数属性。 这些功能通常是创建大多数自动化服务器所需的所有功能。

如果 ClassWizard 支持的宏不足，则可以使用以下附加宏： `DISP_PROPERTY_NOTIFY` 和 `DISP_PROPERTY_PARAM` 。

## <a name="disp_property_notify--macro-description"></a>DISP_PROPERTY_NOTIFY-宏说明

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>parameters

*类*<br/>
类的名称。

*pszName*<br/>
属性的外部名称。

*名称*<br/>
存储属性的成员变量的名称。

*pfnAfterSet*<br/>
更改属性时要调用的成员函数的名称。

*vtPropType*<br/>
一个指定属性类型的值。

### <a name="remarks"></a>备注

此宏非常类似于 DISP_PROPERTY，只不过它接受其他参数。 附加参数 *pfnAfterSet* 应为不返回任何内容且不带参数的成员函数 "void OnPropertyNotify ( # A1"。 在修改成员变量 **后** ，将调用此方法。

## <a name="disp_property_param--macro-description"></a>DISP_PROPERTY_PARAM-宏说明

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>parameters

*类*<br/>
类的名称。

*pszName*<br/>
属性的外部名称。

*memberGet*<br/>
用于获取属性的成员函数的名称。

*集*<br/>
用于设置属性的成员函数的名称。

*vtPropType*<br/>
一个指定属性类型的值。

*vtsParams*<br/>
为每个参数分隔 VTS_ 的字符串。

### <a name="remarks"></a>备注

与 DISP_PROPERTY_EX 宏非常类似，此宏定义使用单独的 Get 和 Set 成员函数访问的属性。 不过，此宏允许您为属性指定参数列表。 这对于实现以其他方式编制索引或参数化的属性很有用。 参数将始终位于第一位，后面是属性的新值。 例如：

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

与 get 和 set 成员函数相对应：

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="disp_xxxx_id--macro-descriptions"></a>DISP_XXXX_ID-宏说明

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>parameters

*类*<br/>
类的名称。

*pszName*<br/>
属性的外部名称。

*dispid*<br/>
此属性或方法的 DISPID。

*pfnGet*<br/>
用于获取属性的成员函数的名称。

*pfnSet*<br/>
用于设置属性的成员函数的名称。

*名称*<br/>
要映射到属性的成员变量的名称。

*vtPropType*<br/>
一个指定属性类型的值。

*vtsParams*<br/>
为每个参数分隔 VTS_ 的字符串。

### <a name="remarks"></a>备注

这些宏允许您指定 **DISPID** ，而不是让 MFC 自动分配一个。 这些高级宏具有相同的名称，但该 ID 附加到宏名称后面 (例如 **DISP_PROPERTY_ID**) ，并且 Id 由 *pszName* 参数之后指定的参数决定。 请参阅 AFXDISP.H&GT。H 有关这些宏的详细信息。 必须将 **_ID** 条目置于调度映射的末尾。 它们将以与非 **_ID** 版本的宏相同的方式影响自动 **DISPID** 生成， (**DISPID** 的由位置) 确定。 例如：

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC 将为类 CDisp3DPoint 生成 Dispid，如下所示：

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

指定固定 **DISPID** 有助于维持之前现有调度接口的向后兼容性，或实现某些系统定义的方法或属性， (通常由消极 **DISPID** 指示，如) **DISPID_NEWENUM** 集合。

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>检索 COleClientItem 的 IDispatch 接口

许多服务器将支持其文档对象内的自动化，以及 OLE 服务器功能。 为了获得对此自动化接口的访问权限，需要直接访问 `COleClientItem::m_lpObject` 成员变量。 下面的代码将检索 `IDispatch` 派生自的对象的接口 `COleClientItem` 。 如果你发现此功能是必需的，则可以在应用程序中包括以下代码：

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

然后，可以将从此函数返回的调度接口直接用于或附加到以 `COleDispatchDriver` 进行类型安全的访问。 如果直接使用此方法，请确保在 `Release` 使用指针时调用其成员 (`COleDispatchDriver` 析构函数默认) 。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
