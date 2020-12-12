---
description: 了解详细信息： CAnimationColor 类
title: CAnimationColor 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
ms.openlocfilehash: 430f017bc9d60eed5e2d42b71f0303546deecaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318632"
---
# <a name="canimationcolor-class"></a>CAnimationColor 类

实现可对颜色的红色、绿色和蓝色分量进行动画处理的颜色功能。

## <a name="syntax"></a>语法

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationColor：： CAnimationColor](#canimationcolor)|已重载。 构造动画颜色对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationColor：： AddTransition](#addtransition)|为红色、绿色和蓝色分量添加转换。|
|[CAnimationColor：： GetB](#getb)|提供对表示蓝色组件的 CAnimationVariable 的访问。|
|[CAnimationColor：： GetDefaultValue](#getdefaultvalue)|返回颜色组件的默认值。|
|[CAnimationColor：： GetG](#getg)|提供对表示绿色组件的 CAnimationVariable 的访问。|
|[CAnimationColor：： GetR](#getr)|提供对表示红色组件的 CAnimationVariable 的访问。|
|[CAnimationColor：： GetValue](#getvalue)|返回当前值。|
|[CAnimationColor：： SetDefaultValue](#setdefaultvalue)|设置默认值。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationColor：： GetAnimationVariableList](#getanimationvariablelist)|将封装的动画变量放入列表中。  (重写 [CAnimationBaseObject：： GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。 ) |

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CAnimationColor：： operator COLORREF](#operator_colorref)||
|[CAnimationColor：： operator =](#operator_eq)|将颜色分配给 CAnimationColor。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationColor：： m_bValue](#m_bvalue)|封装的动画变量，它表示动画颜色的蓝色分量。|
|[CAnimationColor：： m_gValue](#m_gvalue)|封装的动画变量，表示动画颜色的绿色组成部分。|
|[CAnimationColor：： m_rValue](#m_rvalue)|封装的动画变量，它表示动画颜色的红色分量。|

## <a name="remarks"></a>备注

CAnimationColor 类封装三个 CAnimationVariable 对象，并可在应用程序中表示颜色。 例如，您可以使用此类对屏幕上任何对象的颜色进行动画处理 (如文本颜色、背景色等) 。 若要在应用程序中使用此类，只需实例化此类的对象，将其添加到使用 CAnimationController：： AddAnimationObject 的动画控制器，并为每个要应用于红色、绿色和蓝色分量的转换调用 AddTransition。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a> CAnimationColor：： AddTransition

为红色、绿色和蓝色分量添加转换。

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>parameters

*pRTransition*<br/>
红色分量的过渡。

*pGTransition*<br/>
绿色组件的过渡。

*pBTransition*<br/>
蓝色分量的过渡。

### <a name="remarks"></a>备注

调用此函数可将指定的转换添加到要应用于表示颜色组件的动画变量的转换的内部列表。 添加转换时，它们不会立即应用，而是存储在内部列表中。 调用 CAnimationController：： AnimateGroup 时，会将转换应用 (添加到特定) 值的情节提要。 如果不需要将转换应用于其中一个颜色组件，可以传递 NULL。

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a> CAnimationColor：： CAnimationColor

构造 CAnimationColor 对象。

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*color*<br/>
指定默认颜色。

*nGroupID*<br/>
指定组 ID。

*nObjectID*<br/>
指定对象 ID。

*dwUserData*<br/>
指定用户定义数据。

### <a name="remarks"></a>备注

对象是用默认值（红色、绿色、蓝色、对象 ID 和组 ID）构造的，这些值将设置为0。 稍后可以使用 SetDefaultValue 和 SetID 在运行时进行更改。

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationColor：： GetAnimationVariableList

将封装的动画变量放入列表中。

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>parameters

*.lst*<br/>
当函数返回时，它包含指向三个表示红色、绿色和蓝色分量的 CAnimationVariable 对象的指针。

## <a name="canimationcolorgetb"></a><a name="getb"></a> CAnimationColor：： GetB

提供对表示蓝色组件的 CAnimationVariable 的访问。

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>返回值

对表示蓝色组件的封装 CAnimationVariable 的引用。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示蓝色组件的基础 CAnimationVariable。

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationColor：： GetDefaultValue

返回颜色组件的默认值。

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>返回值

一个 COLORREF 值，该值包含 RGB 组件的默认值。

### <a name="remarks"></a>备注

调用此函数可检索以前由构造函数或 SetDefaultValue 设置的默认值。

## <a name="canimationcolorgetg"></a><a name="getg"></a> CAnimationColor：： GetG

提供对表示绿色组件的 CAnimationVariable 的访问。

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>返回值

对封装的 CAnimationVariable 的引用，表示绿色组件。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示绿色组件的基础 CAnimationVariable。

## <a name="canimationcolorgetr"></a><a name="getr"></a> CAnimationColor：： GetR

提供对表示红色组件的 CAnimationVariable 的访问。

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>返回值

对封装的 CAnimationVariable 的引用，表示红色组件。

### <a name="remarks"></a>备注

您可以调用此方法以直接访问表示红色组件的基础 CAnimationVariable。

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a> CAnimationColor：： GetValue

返回当前值。

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>parameters

*color*<br/>
输出。 此方法返回时包含当前值。

### <a name="return-value"></a>返回值

如果已成功检索到当前值，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可检索动画颜色的当前值。 如果此方法失败或颜色组件的基础 COM 对象尚未初始化，则 color 包含默认值，该默认值以前在构造函数或 SetDefaultValue 中设置。

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a> CAnimationColor：： m_bValue

封装的动画变量，它表示动画颜色的蓝色分量。

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a> CAnimationColor：： m_gValue

封装的动画变量，表示动画颜色的绿色组成部分。

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a> CAnimationColor：： m_rValue

封装的动画变量，它表示动画颜色的红色分量。

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a> CAnimationColor：： operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>返回值

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a> CAnimationColor：： operator =

将颜色分配给 CAnimationColor。

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>parameters

*color*<br/>
指定新的值动画颜色。

### <a name="remarks"></a>备注

建议在动画开始之前执行此操作，因为此运算符将调用 SetDefaultValue，这将重新创建颜色组件的基础 COM 对象（如果已创建）。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationColor：： SetDefaultValue

设置默认值。

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>parameters

*color*<br/>
为红色、绿色和蓝色分量指定新的默认值。

### <a name="remarks"></a>备注

使用此函数可将默认值设置为动画对象。 此方法将默认值分配给动画颜色的颜色部分。 如果已创建基础 COM 对象，它还会重新创建它们。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
