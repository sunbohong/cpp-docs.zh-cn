---
description: 了解详细信息： CSinusoidalTransitionFromRange 类
title: CSinusoidalTransitionFromRange 类
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: 5d00b1cbfb8fe9b76a5a69bd1c9f10316ddf8141
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264565"
---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange 类

封装具有给定振动范围的正弦范围转换。

## <a name="syntax"></a>语法

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSinusoidalTransitionFromRange：： CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|构造转换对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSinusoidalTransitionFromRange：： Create](#create)|调用转换库以创建封装的转换 COM 对象。  (重写 [CBaseTransition：： Create](../../mfc/reference/cbasetransition-class.md#create). ) |

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CSinusoidalTransitionFromRange：： m_dblMaximumValue](#m_dblmaximumvalue)|正弦 wave 高峰的动画变量的值。|
|[CSinusoidalTransitionFromRange：： m_dblMinimumValue](#m_dblminimumvalue)|正弦 wave 的通过上的动画变量的值。|
|[CSinusoidalTransitionFromRange：： m_duration](#m_duration)|转换的持续时间。|
|[CSinusoidalTransitionFromRange：： m_period](#m_period)|正弦波的振荡时间（秒）。|
|[CSinusoidalTransitionFromRange：： m_slope](#m_slope)|转换开头的斜率。|

## <a name="remarks"></a>备注

动画变量的值会在正弦范围转换的整个持续时间内，在指定的最小值和最大值之间波动。 斜率参数用于区分其他参数指定的两个可能的正弦波之间的歧义。 由于所有转换都将自动清除，因此建议使用 operator new 将其分配给它们。 封装的 IUIAnimationTransition COM 对象由 CAnimationController：： AnimateGroup 创建，直到它为 NULL。 在创建此 COM 对象之后更改成员变量不起作用。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a> CSinusoidalTransitionFromRange：： Create

调用转换库以创建封装的转换 COM 对象。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>parameters

*pLibrary*<br/>
指向转换库的指针，它负责创建标准转换。

### <a name="return-value"></a>返回值

如果成功创建转换，则为 TRUE;否则为 FALSE。

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a> CSinusoidalTransitionFromRange：： CSinusoidalTransitionFromRange

构造转换对象。

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

*dblMinimumValue*<br/>
正弦 wave 的通过上的动画变量的值。

*dblMaximumValue*<br/>
正弦 wave 高峰的动画变量的值。

*同期*<br/>
正弦波的振荡时间（秒）。

*斜*<br/>
转换开头的斜率。

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a> CSinusoidalTransitionFromRange：： m_dblMaximumValue

正弦 wave 高峰的动画变量的值。

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a> CSinusoidalTransitionFromRange：： m_dblMinimumValue

正弦 wave 的通过上的动画变量的值。

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a> CSinusoidalTransitionFromRange：： m_duration

转换的持续时间。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a> CSinusoidalTransitionFromRange：： m_period

正弦波的振荡时间（秒）。

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a> CSinusoidalTransitionFromRange：： m_slope

转换开头的斜率。

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
