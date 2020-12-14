---
description: 了解详细信息： CCustomInterpolator 类
title: CCustomInterpolator 类
ms.date: 11/04/2016
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
ms.openlocfilehash: 84fcdc20ce1a90441a508f1469d498095980af83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227749"
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator 类

实现基本插值程序。

## <a name="syntax"></a>语法

```
class CCustomInterpolator;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CCustomInterpolator：： CCustomInterpolator](#ccustominterpolator)|已重载。 构造自定义内插的对象，并将持续时间和速度初始化为指定值。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CCustomInterpolator：： GetDependencies](#getdependencies)|获取内插程序的依赖项。|
|[CCustomInterpolator：： GetDuration](#getduration)|获取内插程序的持续时间。|
|[CCustomInterpolator：： GetFinalValue](#getfinalvalue)|获取该内插的最终值。|
|[CCustomInterpolator：： Init](#init)|初始化持续时间和最终值。|
|[CCustomInterpolator：： InterpolateValue](#interpolatevalue)|按给定的偏移量内插值。|
|[CCustomInterpolator：： InterpolateVelocity](#interpolatevelocity)|按给定的偏移量内插速度|
|[CCustomInterpolator：： SetDuration](#setduration)|设置内插程序的持续时间。|
|[CCustomInterpolator：： SetInitialValueAndVelocity](#setinitialvalueandvelocity)|设置内插程序的初始值和速度。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CCustomInterpolator：： m_currentValue](#m_currentvalue)|内插值。|
|[CCustomInterpolator：： m_currentVelocity](#m_currentvelocity)|内插速度。|
|[CCustomInterpolator：： m_duration](#m_duration)|转换的持续时间。|
|[CCustomInterpolator：： m_finalValue](#m_finalvalue)|转换结束时变量的最终值。|
|[CCustomInterpolator：： m_initialValue](#m_initialvalue)|转换开始时变量的值。|
|[CCustomInterpolator：： m_initialVelocity](#m_initialvelocity)|变量在转换开始时的速度。|

## <a name="remarks"></a>备注

从 CCustomInterpolator 派生一个类，并重写所有必要的方法以实现自定义内插算法。 指向此类的指针应作为参数传递给 CCustomTransition。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CCustomInterpolator`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a> CCustomInterpolator：： CCustomInterpolator

构造一个自定义内插的对象，并将所有值设置为默认值0。

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

*finalValue*

### <a name="remarks"></a>备注

使用 CCustomInterpolator：： Init 初始化代码中的持续时间和最终值。

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a> CCustomInterpolator：： GetDependencies

获取内插程序的依赖项。

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>parameters

*initialValueDependencies*<br/>
输出。 依赖于传递给 SetInitialValueAndVelocity 的初始值的内插程序的各个方面。

*initialVelocityDependencies*<br/>
输出。 取决于传递到 SetInitialValueAndVelocity 的初始速度的内插程序的各个方面。

*durationDependencies*<br/>
输出。 取决于传递到 SetDuration 的持续时间的内插程序的各个方面。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a> CCustomInterpolator：： GetDuration

获取内插程序的持续时间。

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>parameters

*duration*<br/>
输出。 转换的持续时间（以秒为单位）。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a> CCustomInterpolator：： GetFinalValue

获取该内插的最终值。

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>参数

*value*<br/>
输出。 转换结束时变量的最终值。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="ccustominterpolatorinit"></a><a name="init"></a> CCustomInterpolator：： Init

初始化持续时间和最终值。

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

*finalValue*<br/>
转换结束时变量的最终值。

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a> CCustomInterpolator：： InterpolateValue

按给定的偏移量内插值。

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>参数

*value*<br/>
输出。 内插值。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a> CCustomInterpolator：： InterpolateVelocity

按给定的偏移量内插速度

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>parameters

*速度*<br/>
输出。 变量在偏移量处的速度。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a> CCustomInterpolator：： m_currentValue

内插值。

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a> CCustomInterpolator：： m_currentVelocity

内插速度。

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a> CCustomInterpolator：： m_duration

转换的持续时间。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a> CCustomInterpolator：： m_finalValue

转换结束时变量的最终值。

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a> CCustomInterpolator：： m_initialValue

转换开始时变量的值。

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomInterpolator：： m_initialVelocity

变量在转换开始时的速度。

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a> CCustomInterpolator：： SetDuration

设置内插程序的持续时间。

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> CCustomInterpolator：： SetInitialValueAndVelocity

设置内插程序的初始值和速度。

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>parameters

*initialValue*<br/>
转换开始时变量的值。

*initialVelocity*<br/>
变量在转换开始时的速度。

### <a name="return-value"></a>返回值

基本实现始终返回 TRUE。 如果希望事件失败，请从重写的实现中返回 FALSE。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
