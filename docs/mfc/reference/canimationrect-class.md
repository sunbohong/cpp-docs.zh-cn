---
description: 了解详细信息： CAnimationRect 类
title: CAnimationRect 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
ms.openlocfilehash: 590b1382992a32e0eb3d49e0ea562d10193c1990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207886"
---
# <a name="canimationrect-class"></a>CAnimationRect 类

实现可对矩形边进行动画处理的矩形功能。

## <a name="syntax"></a>语法

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationRect：： CAnimationRect](#canimationrect)|已重载。 构造动画矩形对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationRect：： AddTransition](#addtransition)|为左、上、右和下坐标添加转换。|
|[CAnimationRect：： GetBottom](#getbottom)|提供对表示下坐标的 CAnimationVariable 的访问。|
|[CAnimationRect：： GetDefaultValue](#getdefaultvalue)|返回矩形边界的默认值。|
|[CAnimationRect：： Shapes.getleft](#getleft)|提供对 CAnimationVariable 的访问，表示左坐标。|
|[CAnimationRect：： GetRight](#getright)|提供对表示右坐标的 CAnimationVariable 的访问。|
|[CAnimationRect：： Shapes.gettop](#gettop)|提供对表示 top 坐标的 CAnimationVariable 的访问。|
|[CAnimationRect：： GetValue](#getvalue)|返回当前值。|
|[CAnimationRect：： SetDefaultValue](#setdefaultvalue)|设置默认值。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationRect：： GetAnimationVariableList](#getanimationvariablelist)|将封装的动画变量放入列表中。  (重写 [CAnimationBaseObject：： GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。 ) |

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CAnimationRect：： operator RECT](#operator_rect)|将 CAnimationRect 转换为 RECT。|
|[CAnimationRect：： operator =](#operator_eq)|将矩形赋给 CAnimationRect。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationRect：： m_bFixedSize](#m_bfixedsize)|指定矩形是否具有固定大小。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationRect：： m_bottomValue](#m_bottomvalue)|封装的动画变量，它表示动画矩形的下边界。|
|[CAnimationRect：： m_leftValue](#m_leftvalue)|封装的动画变量，表示动画矩形的左边界。|
|[CAnimationRect：： m_rightValue](#m_rightvalue)|封装的动画变量，它表示动画矩形的右边界。|
|[CAnimationRect：： m_szInitial](#m_szinitial)|指定动画矩形的初始大小。|
|[CAnimationRect：： m_topValue](#m_topvalue)|封装的动画变量，它表示动画矩形的上边界。|

## <a name="remarks"></a>备注

CAnimationRect 类封装四个 CAnimationVariable 对象，并可在应用程序中表示矩形。 若要在应用程序中使用此类，只需实例化此类的对象，将其添加到使用 CAnimationController：： AddAnimationObject 的动画控制器，并为每个要应用于左、右上和下坐标的转换调用 AddTransition。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a> CAnimationRect：： AddTransition

为左、上、右和下坐标添加转换。

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>parameters

*pLeftTransition*<br/>
指定左侧的转换。

*pTopTransition*<br/>
指定顶部的转换。

*pRightTransition*<br/>
指定右侧的转换。

*pBottomTransition*<br/>
指定底部的转换。

### <a name="remarks"></a>备注

调用此函数可将指定的转换添加到要应用于每个矩形边的动画变量的转换的内部列表。 添加转换时，它们不会立即应用，而是存储在内部列表中。 调用 CAnimationController：： AnimateGroup 时，会将转换应用 (添加到特定) 值的情节提要。 如果不需要将转换应用于其中一个矩形边，可以传递 NULL。

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a> CAnimationRect：： CAnimationRect

构造 CAnimationRect 对象。

```
CAnimationRect();

CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*rect*<br/>
指定默认矩形。

*nGroupID*<br/>
指定组 ID。

*nObjectID*<br/>
指定对象 ID。

*dwUserData*<br/>
指定用户定义数据。

*pt*<br/>
左上角的坐标。

*sz*<br/>
矩形的大小。

*nLeft*<br/>
指定左边界的坐标。

*nTop*<br/>
指定顶部边界的坐标。

*nRight*<br/>
指定右边界的坐标。

*nBottom*<br/>
指定下边界的坐标。

### <a name="remarks"></a>备注

对象是用默认值（左侧、顶部、右侧和底部）、对象 ID 和组 ID （将设置为0）构造的。 稍后可以使用 SetDefaultValue 和 SetID 在运行时进行更改。

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationRect：： GetAnimationVariableList

将封装的动画变量放入列表中。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>parameters

*.lst*<br/>
当函数返回时，它包含指向四个 CAnimationVariable 对象的指针，这些对象表示矩形的坐标。

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a> CAnimationRect：： GetBottom

提供对表示下坐标的 CAnimationVariable 的访问。

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>返回值

对封装的 CAnimationVariable 的引用，表示底部坐标。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示底部坐标的基础 CAnimationVariable。

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationRect：： GetDefaultValue

返回矩形边界的默认值。

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>返回值

一个 CRect 值，该值包含左、右、上和下的默认值。

### <a name="remarks"></a>备注

调用此函数可检索以前由构造函数或 SetDefaultValue 设置的默认值。

## <a name="canimationrectgetleft"></a><a name="getleft"></a> CAnimationRect：： Shapes.getleft

提供对 CAnimationVariable 的访问，表示左坐标。

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>返回值

对封装的 CAnimationVariable 的引用，表示左坐标。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示左边坐标的基础 CAnimationVariable。

## <a name="canimationrectgetright"></a><a name="getright"></a> CAnimationRect：： GetRight

提供对表示右坐标的 CAnimationVariable 的访问。

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>返回值

对封装的 CAnimationVariable 的引用，表示正确的坐标。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示右坐标的基础 CAnimationVariable。

## <a name="canimationrectgettop"></a><a name="gettop"></a> CAnimationRect：： Shapes.gettop

提供对表示 top 坐标的 CAnimationVariable 的访问。

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>返回值

表示 top 坐标的封装 CAnimationVariable 的引用。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示顶层坐标的基础 CAnimationVariable。

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a> CAnimationRect：： GetValue

返回当前值。

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>parameters

*rect*<br/>
输出。 此方法返回时包含当前值。

### <a name="return-value"></a>返回值

如果已成功检索到当前值，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可检索动画矩形的当前值。 如果此方法失败或左侧、顶部、右侧和底部的基础 COM 对象尚未初始化，则 rect 包含默认值，该默认值以前在构造函数或 SetDefaultValue 中设置。

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a> CAnimationRect：： m_bFixedSize

指定矩形是否具有固定大小。

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>备注

如果此成员为 true，则在每次按照固定大小移动左上角时，矩形的大小是固定的，并重新计算右侧值和下限值。 将此值设置为 TRUE 可轻松地在屏幕上移动矩形。 在这种情况下，将忽略应用于右和下坐标的转换。 构造对象和/或调用 SetDefaultValue 时，会在内部存储大小。 默认情况下，此成员设置为 FALSE。

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a> CAnimationRect：： m_bottomValue

封装的动画变量，它表示动画矩形的下边界。

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a> CAnimationRect：： m_leftValue

封装的动画变量，表示动画矩形的左边界。

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a> CAnimationRect：： m_rightValue

封装的动画变量，它表示动画矩形的右边界。

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a> CAnimationRect：： m_szInitial

指定动画矩形的初始大小。

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a> CAnimationRect：： m_topValue

封装的动画变量，它表示动画矩形的上边界。

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a> CAnimationRect：： operator RECT

将 CAnimationRect 转换为 RECT。

```
operator RECT();
```

### <a name="return-value"></a>返回值

矩形形式的动画矩形的当前值。

### <a name="remarks"></a>备注

此函数在内部调用 GetValue。 如果 GetValue 出于某种原因失败，则返回的矩形将包含所有矩形坐标的默认值。

## <a name="canimationrectoperator"></a><a name="operator_eq"></a> CAnimationRect：： operator =

将矩形赋给 CAnimationRect。

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>parameters

*rect*<br/>
动画矩形的新值。

### <a name="remarks"></a>备注

建议在动画开始之前执行此操作，因为此运算符将调用 SetDefaultValue，这将重新创建颜色组件的基础 COM 对象（如果已创建）。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationRect：： SetDefaultValue

设置默认值。

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>parameters

*rect*<br/>
为左、上、右和下指定新的默认值。

### <a name="remarks"></a>备注

使用此函数可将默认值设置为动画对象。 此方法将默认值分配给矩形的界限。 如果已创建基础 COM 对象，它还会重新创建它们。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
