---
description: 了解详细信息： CAnimationPoint 类
title: CAnimationPoint 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
ms.openlocfilehash: ddefb93950f0ff1109478f3574413faf9f60a22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336787"
---
# <a name="canimationpoint-class"></a>CAnimationPoint 类

实现可对点坐标进行动画处理的点功能。

## <a name="syntax"></a>语法

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationPoint：： CAnimationPoint](#canimationpoint)|已重载。 构造 CAnimationPoint 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationPoint：： AddTransition](#addtransition)|为 X 和 Y 坐标添加转换。|
|[CAnimationPoint：： GetDefaultValue](#getdefaultvalue)|返回 X 和 Y 坐标的默认值。|
|[CAnimationPoint：： GetValue](#getvalue)|返回当前值。|
|[CAnimationPoint：： GetX](#getx)|为 X 坐标提供对 CAnimationVariable 的访问。|
|[CAnimationPoint：： GetY](#gety)|提供对 CAnimationVariable for Y 坐标的访问。|
|[CAnimationPoint：： SetDefaultValue](#setdefaultvalue)|设置默认值。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationPoint：： GetAnimationVariableList](#getanimationvariablelist)|将封装的动画变量放入列表中。  (重写 [CAnimationBaseObject：： GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。 ) |

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CAnimationPoint：： operator CPoint](#operator_cpoint)|将 CAnimationPoint 转换为 CPoint。|
|[CAnimationPoint：： operator =](#operator_eq)|将 ptSrc 分配给 CAnimationPoint。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationPoint：： m_xValue](#m_xvalue)|封装的动画变量，表示动画点的 X 坐标。|
|[CAnimationPoint：： m_yValue](#m_yvalue)|封装的动画变量，它表示动画点的 Y 坐标。|

## <a name="remarks"></a>备注

CAnimationPoint 类封装两个 CAnimationVariable 对象，并可在应用程序中表示点。 例如，你可以使用此类对屏幕上任何对象的位置进行动画处理 (如文本字符串、圆圈、点等) 。 若要在应用程序中使用此类，只需实例化此类的对象，将其添加到使用 CAnimationController：： AddAnimationObject 的动画控制器，并为每个要应用于 X 和/或 Y 坐标的转换调用 AddTransition。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a> CAnimationPoint：： AddTransition

为 X 和 Y 坐标添加转换。

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>parameters

*pXTransition*<br/>
指向 X 坐标的转换的指针。

*pYTransition*<br/>
指向 Y 坐标的转换的指针。

### <a name="remarks"></a>备注

调用此函数可将指定的转换添加到要应用于 X 和 Y 坐标的动画变量的转换的内部列表。 添加转换时，它们不会立即应用，而是存储在内部列表中。 调用 CAnimationController：： AnimateGroup 时，会将转换应用 (添加到特定) 值的情节提要。 如果不需要将转换应用于坐标之一，可以传递 NULL。

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a> CAnimationPoint：： CAnimationPoint

构造 CAnimationPoint 对象。

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*ptDefault*<br/>
指定默认点坐标。

*nGroupID*<br/>
指定组 ID。

*nObjectID*<br/>
指定对象 ID。

*dwUserData*<br/>
指定用户定义数据。

### <a name="remarks"></a>备注

用默认属性构造 CAnimationPoint 对象：默认点坐标、组 ID 和对象 ID 设置为0。

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationPoint：： GetAnimationVariableList

将封装的动画变量放入列表中。

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>parameters

*.lst*<br/>
当函数返回时，它包含指向两个表示 X 和 Y 坐标的 CAnimationVariable 对象的指针。

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationPoint：： GetDefaultValue

返回 X 和 Y 坐标的默认值。

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>返回值

包含默认值的点。

### <a name="remarks"></a>备注

调用此函数可检索以前由构造函数或 SetDefaultValue 设置的默认值。

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a> CAnimationPoint：： GetValue

返回当前值。

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>parameters

*ptValue*<br/>
输出。 此方法返回时包含当前值。

### <a name="return-value"></a>返回值

如果已成功检索到当前值，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可检索动画点的当前值。 如果此方法失败或 X 和 Y 坐标的基础 COM 对象尚未初始化，则 ptValue 将包含以前在构造函数或 SetDefaultValue 中设置的默认值。

## <a name="canimationpointgetx"></a><a name="getx"></a> CAnimationPoint：： GetX

为 X 坐标提供对 CAnimationVariable 的访问。

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>返回值

表示 X 坐标的封装 CAnimationVariable 的引用。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示 X 坐标的基础 CAnimationVariable。

## <a name="canimationpointgety"></a><a name="gety"></a> CAnimationPoint：： GetY

提供对 CAnimationVariable for Y 坐标的访问。

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>返回值

一个表示 Y 坐标的封装 CAnimationVariable 的引用。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示 Y 坐标的基础 CAnimationVariable。

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a> CAnimationPoint：： m_xValue

封装的动画变量，表示动画点的 X 坐标。

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a> CAnimationPoint：： m_yValue

封装的动画变量，它表示动画点的 Y 坐标。

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a> CAnimationPoint：： operator CPoint

将 CAnimationPoint 转换为 CPoint。

```
operator CPoint();
```

### <a name="return-value"></a>返回值

CAnimationPoint 的当前值为 CPoint。

### <a name="remarks"></a>备注

此函数在内部调用 GetValue。 如果 GetValue 出于某种原因失败，则返回的点将包含 X 和 Y 坐标的默认值。

## <a name="canimationpointoperator"></a><a name="operator_eq"></a> CAnimationPoint：： operator =

将 ptSrc 分配给 CAnimationPoint。

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>parameters

*ptSrc*<br/>
引用 CPoint 或 POINT。

### <a name="remarks"></a>备注

将 ptSrc 分配给 CAnimationPoint。 建议在动画开始之前执行此操作，因为此运算符将调用 SetDefaultValue，这将重新创建 X 和 Y 坐标的基础 COM 对象（如果已创建）。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationPoint：： SetDefaultValue

设置默认值。

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>parameters

*ptDefault*<br/>
指定默认的点值。

### <a name="remarks"></a>备注

使用此函数可将默认值设置为动画对象。 此方法将默认值分配给动画点的 X 和 Y 坐标。 如果已创建基础 COM 对象，它还会重新创建它们。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
