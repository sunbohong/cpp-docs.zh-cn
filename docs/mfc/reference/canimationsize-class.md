---
description: 了解详细信息： CAnimationSize 类
title: CAnimationSize 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: 894675c485077291c3fca35acfb9bfa9a3d10286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336767"
---
# <a name="canimationsize-class"></a>CAnimationSize 类

实现可对大小对象的维度进行动画处理的大小对象功能。

## <a name="syntax"></a>语法

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationSize：： CAnimationSize](#canimationsize)|已重载。 构造动画大小对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationSize：： AddTransition](#addtransition)|添加宽度和高度的转换。|
|[CAnimationSize：： GetCX](#getcx)|提供对表示 Width 的 CAnimationVariable 的访问。|
|[CAnimationSize：： GetCY](#getcy)|提供对表示高度的 CAnimationVariable 的访问。|
|[CAnimationSize：： GetDefaultValue](#getdefaultvalue)|返回宽度和高度的默认值。|
|[CAnimationSize：： GetValue](#getvalue)|返回当前值。|
|[CAnimationSize：： SetDefaultValue](#setdefaultvalue)|设置默认值。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationSize：： GetAnimationVariableList](#getanimationvariablelist)|将封装的动画变量放入列表中。  (重写 [CAnimationBaseObject：： GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。 ) |

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CAnimationSize：： operator CSize](#operator_csize)|将 CAnimationSize 转换为 CSize。|
|[CAnimationSize：： operator =](#operator_eq)|将 szSrc 分配给 CAnimationSize。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationSize：： m_cxValue](#m_cxvalue)|封装的动画变量，它表示动画大小的宽度。|
|[CAnimationSize：： m_cyValue](#m_cyvalue)|封装的动画变量，表示动画大小的高度。|

## <a name="remarks"></a>备注

CAnimationSize 类封装两个 CAnimationVariable 对象，并可在应用程序中表示大小。 例如，您可以使用此类对屏幕上任意二维对象的大小进行动画处理 (如矩形、控件等) 。 若要在应用程序中使用此类，只需实例化此类的对象，将其添加到使用 CAnimationController：： AddAnimationObject 的动画控制器，并为每个要应用于宽度和/或高度的转换调用 AddTransition。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a> CAnimationSize：： AddTransition

添加宽度和高度的转换。

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>parameters

*pCXTransition*<br/>
指向 Width 转换的指针。

*pCYTransition*<br/>
指向高度转换的指针。

### <a name="remarks"></a>备注

调用此函数可将指定的转换添加到要应用于宽度和高度动画变量的转换的内部列表。 添加转换时，它们不会立即应用，而是存储在内部列表中。 调用 CAnimationController：： AnimateGroup 时，会将转换应用 (添加到特定) 值的情节提要。 如果不需要将转换应用到某个维度，可以传递 NULL。

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a> CAnimationSize：： CAnimationSize

构造动画大小对象。

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*szDefault*<br/>
指定默认大小。

*nGroupID*<br/>
指定组 ID。

*nObjectID*<br/>
指定对象 ID。

*dwUserData*<br/>
指定用户定义数据。

### <a name="remarks"></a>备注

对象是用默认值（宽度、高度、对象 ID 和组 ID）构造的，这些值将设置为0。 稍后可以使用 SetDefaultValue 和 SetID 在运行时进行更改。

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationSize：： GetAnimationVariableList

将封装的动画变量放入列表中。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>parameters

*.lst*<br/>
当函数返回时，它包含指向两个表示宽度和高度的 CAnimationVariable 对象的指针。

## <a name="canimationsizegetcx"></a><a name="getcx"></a> CAnimationSize：： GetCX

提供对表示 Width 的 CAnimationVariable 的访问。

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>返回值

表示宽度的封装 CAnimationVariable 的引用。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示 Width 的基础 CAnimationVariable。

## <a name="canimationsizegetcy"></a><a name="getcy"></a> CAnimationSize：： GetCY

提供对表示高度的 CAnimationVariable 的访问。

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>返回值

表示高度的封装 CAnimationVariable 的引用。

### <a name="remarks"></a>备注

可以调用此方法以直接访问表示高度的基础 CAnimationVariable。

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationSize：： GetDefaultValue

返回宽度和高度的默认值。

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>返回值

包含默认值的 CSize 对象。

### <a name="remarks"></a>备注

调用此函数可检索以前由构造函数或 SetDefaultValue 设置的默认值。

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a> CAnimationSize：： GetValue

返回当前值。

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>parameters

*szValue*<br/>
输出。 此方法返回时包含当前值。

### <a name="return-value"></a>返回值

如果已成功检索到当前值，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可检索动画大小的当前值。 如果此方法失败或尚未初始化 Width 和 Size 的基础 COM 对象，则 szValue 将包含以前在构造函数或 SetDefaultValue 中设置的默认值。

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a> CAnimationSize：： m_cxValue

封装的动画变量，它表示动画大小的宽度。

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a> CAnimationSize：： m_cyValue

封装的动画变量，表示动画大小的高度。

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a> CAnimationSize：： operator CSize

将 CAnimationSize 转换为 CSize。

```
operator CSize();
```

### <a name="return-value"></a>返回值

动画大小的当前值为 CSize。

### <a name="remarks"></a>备注

此函数在内部调用 GetValue。 如果 GetValue 出于某种原因失败，则返回的大小将包含宽度和高度的默认值。

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a> CAnimationSize：： operator =

将 szSrc 分配给 CAnimationSize。

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>parameters

*szSrc*<br/>
引用 CSize 或 SIZE。

### <a name="remarks"></a>备注

将 szSrc 分配给 CAnimationSize。 建议在动画开始之前执行此操作，因为此运算符将调用 SetDefaultValue，这将重新创建基础 COM 对象的宽度和高度（如果已创建）。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationSize：： SetDefaultValue

设置默认值。

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>parameters

*szDefault*<br/>
指定新的默认大小。

### <a name="remarks"></a>备注

使用此函数可将默认值设置为动画对象。 此方法将默认值分配给动画大小的宽度和高度。 如果已创建基础 COM 对象，它还会重新创建它们。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
