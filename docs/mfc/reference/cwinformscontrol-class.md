---
description: 了解详细信息： CWinFormsControl 类
title: CWinFormsControl 类
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: 32daf5f1bf9efcd5d5b17d134dc8deaee7e32527
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318437"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl 类

提供用于承载 Windows 窗体控件的基本功能。

## <a name="syntax"></a>语法

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>parameters

*TManagedControl*<br/>
要在 MFC 应用程序中显示的 .NET Framework Windows 窗体控件。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|构造 MFC Windows 窗体控件包装对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|在 MFC 容器中创建一个 Windows 窗体控件。|
|[CWinFormsControl::GetControl](#getcontrol)|检索指向 Windows 窗体控件的指针。|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|检索 Windows 窗体控件的句柄。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CWinFormsControl：： operator-&gt;](#operator_-_gt)|替换表达式中的 [CWinFormsControl：： GetControl](#getcontrol) 。|
|[CWinFormsControl：： operator TManagedControl ^](#operator_tmanagedcontrol)|将类型强制转换为指向 Windows 窗体控件的指针。|

## <a name="remarks"></a>备注

`CWinFormsControl`类提供用于承载 Windows 窗体控件的基本功能。

有关使用 Windows 窗体的详细信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

MFC 代码不应缓存窗口句柄， (通常存储在 `m_hWnd`) 中。 某些 Windows 窗体控件属性要求 `Window` 使用和重新创建基础 Win32 `DestroyWindow` `CreateWindow` 。 MFC Windows 窗体实现处理 `Destroy` `Create` 用于更新成员的控件的和事件 `m_hWnd` 。

> [!NOTE]
> MFC Windows 窗体集成仅适用于使用 MFC (动态链接的项目，其中定义了 AFXDLL) 。

## <a name="requirements"></a>要求

**标头：** afxwinforms

## <a name="cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a> CWinFormsControl::CreateManagedControl

在 MFC 容器中创建一个 Windows 窗体控件。

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>parameters

*pType*<br/>
要创建的控件的数据类型。 必须是 [类型](/dotnet/api/system.type) 数据类型。

*dwStyle*<br/>
要应用于控件的窗口样式。 指定 [窗口样式](../../mfc/reference/styles-used-by-mfc.md#window-styles)的组合。 目前仅支持以下样式： WS_TABSTOP、WS_VISIBLE、WS_DISABLED 和 WS_GROUP。

*rect*<br/>
[矩形结构](/windows/win32/api/windef/ns-windef-rect)，定义仅)  (第一个重载的控件的左上角和右下角的坐标。

*nPlaceHolderID*<br/>
放置在资源编辑器中的静态占位符控件的句柄。 新创建的 Windows 窗体控件将替换静态控件，假设其位置、z 顺序和样式 (第二个重载仅) 。

*pParentWnd*<br/>
指向父窗口的指针。

*nID*<br/>
要分配给新创建的控件的资源 ID 号。

*pControl*<br/>
要与 [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) 对象关联的 Windows 窗体控件的实例， (第四个重载只) 。

### <a name="return-value"></a>返回值

如果成功，则返回一个非零值。 如果不成功，则返回零。

### <a name="remarks"></a>备注

此方法实例化 MFC 容器中的 .NET Framework Windows 窗体控件。

方法的第一个重载接受 .NET Framework 数据类型 *pType* ，以便 MFC 可以实例化此类型的新对象。 *pType* 必须是 [类型](/dotnet/api/system.type) 数据类型。

方法的第二个重载根据类的模板参数创建一个 Windows 窗体控件 `TManagedControl` `CWinFormsControl` 。 控件的大小和位置基于 `RECT` 传递给方法的结构。 只有样式的 *dwStyle* 问题。

方法的第三个重载创建一个 Windows 窗体控件，该控件将替换静态控件，并将其销毁并假设其位置、z 顺序和样式。 静态控件只能用作 Windows 窗体控件的占位符。 创建控件时，此重载将 *dwStyle* 中的样式与静态控件的资源样式组合在一起。

使用方法的第四个重载，可以传入已经实例化的、Windows 窗体 MFC 将包装的控件 *pControl* 。 它必须与类的模板参数属于同一类型 `TManagedControl` `CWinFormsControl` 。

有关使用 Windows 窗体控件的示例，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 。

## <a name="cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a> CWinFormsControl::CWinFormsControl

构造 MFC Windows 窗体控件包装对象。

```
CWinFormsControl();
```

### <a name="remarks"></a>备注

调用 [CWinFormsControl：： CreateManagedControl](#createmanagedcontrol)时，将实例化 Windows 窗体控件。

## <a name="cwinformscontrolgetcontrol"></a><a name="getcontrol"></a> CWinFormsControl::GetControl

检索指向 Windows 窗体控件的指针。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>返回值

返回一个指向 Windows 窗体控件的指针。

### <a name="example"></a>示例

  请参阅 [CWinFormsControl：： CreateManagedControl](#createmanagedcontrol)。

## <a name="cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a> CWinFormsControl::GetControlHandle

检索 Windows 窗体控件的句柄。

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>返回值

返回 Windows 窗体控件的句柄。

### <a name="remarks"></a>备注

`GetControlHandle` 是一个帮助器方法，它返回存储在 .NET Framework 控件属性中的窗口句柄。 调用[cwnd：： Attach](../../mfc/reference/cwnd-class.md#attach)期间，会将窗口句柄值复制到[cwnd：： m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) 。

## <a name="cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a> CWinFormsControl：： operator-&gt;

替换表达式中的 [CWinFormsControl：： GetControl](#getcontrol) 。

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>备注

此运算符提供了一个方便的语法，可 `GetControl` 在表达式中进行替换。

有关 Windows 窗体的详细信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

## <a name="cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a> CWinFormsControl：： operator TManagedControl ^

将类型强制转换为指向 Windows 窗体控件的指针。

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>备注

此运算符传递 `CWinFormsControl<TManagedControl>` 到接受指向 Windows 窗体控件的指针的函数。

## <a name="see-also"></a>请参阅

[CWinFormsDialog 类](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CWinFormsView 类](../../mfc/reference/cwinformsview-class.md)
