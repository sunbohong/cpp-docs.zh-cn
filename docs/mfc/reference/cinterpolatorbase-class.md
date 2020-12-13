---
description: 了解详细信息： CInterpolatorBase 类
title: CInterpolatorBase 类
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: 73204e8b81db862fe30058d1b2451ea468d332e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340952"
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase 类

实现回调，它在必须计算动画变量的新值时由动画 API 调用。

## <a name="syntax"></a>语法

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CInterpolatorBase：： CInterpolatorBase](#cinterpolatorbase)|构造 `CInterpolatorBase` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CInterpolatorBase：： CreateInstance](#createinstance)|创建的实例 `CInterpolatorBase` ，并存储指向将处理事件的自定义内插程序的指针。|
|[CInterpolatorBase：： GetDependencies](#getdependencies)|获取内插程序的依赖项。 （重写 `CUIAnimationInterpolatorBase::GetDependencies`。）|
|[CInterpolatorBase：： GetDuration](#getduration)|获取内插程序的持续时间。 （重写 `CUIAnimationInterpolatorBase::GetDuration`。）|
|[CInterpolatorBase：： GetFinalValue](#getfinalvalue)|获取该内插的最终值。 （重写 `CUIAnimationInterpolatorBase::GetFinalValue`。）|
|[CInterpolatorBase：： InterpolateValue](#interpolatevalue)|按给定的偏移量将值内插 (重写 `CUIAnimationInterpolatorBase::InterpolateValue` 。 ) |
|[CInterpolatorBase：： InterpolateVelocity](#interpolatevelocity)|按给定的偏移量将速度内插 (重写 `CUIAnimationInterpolatorBase::InterpolateVelocity` 。 ) |
|[CInterpolatorBase：： SetCustomInterpolator](#setcustominterpolator)|存储一个指向自定义内插的指针，该指针将处理事件。|
|[CInterpolatorBase：： SetDuration](#setduration)|设置插值 (重写的持续时间 `CUIAnimationInterpolatorBase::SetDuration` 。 ) |
|[CInterpolatorBase：： SetInitialValueAndVelocity](#setinitialvalueandvelocity)|设置内插程序的初始值和速度。 （重写 `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`。）|

## <a name="remarks"></a>备注

创建对象时，将创建该处理程序，并将其传递给 `IUIAnimationTransitionFactory::CreateTransition` `CCustomTransition` 作为动画初始化过程的一部分的对象 (`CAnimationController::AnimateGroup`) 启动。 通常不需要直接使用此类，它只是将所有事件从者到 `CCustomInterpolator` 派生类中，其指针传递到的构造函数 `CCustomTransition` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a> CInterpolatorBase：： CInterpolatorBase

构造 CInterpolatorBase 对象。

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a> CInterpolatorBase：： CreateInstance

创建 CInterpolatorBase 的实例，并存储指向将处理事件的自定义内插程序的指针。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>parameters

*pInterpolator*<br/>
指向自定义内插的指针。

*ppHandler*<br/>
输出。 当函数返回时，包含指向 CInterpolatorBase 实例的指针。

### <a name="return-value"></a>返回值

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a> CInterpolatorBase：： GetDependencies

获取内插程序的依赖项。

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>parameters

*initialValueDependencies*<br/>
输出。 依赖于传递给 SetInitialValueAndVelocity 的初始值的内插程序的各个方面。

*initialVelocityDependencies*<br/>
输出。 取决于传递到 SetInitialValueAndVelocity 的初始速度的内插程序的各个方面。

*durationDependencies*<br/>
输出。 取决于传递到 SetDuration 的持续时间的内插程序的各个方面。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 GetDependencies 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a> CInterpolatorBase：： GetDuration

获取内插程序的持续时间。

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>parameters

*duration*<br/>
输出。 转换的持续时间（以秒为单位）。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 GetDuration 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a> CInterpolatorBase：： GetFinalValue

获取该内插的最终值。

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>参数

*value*<br/>
输出。 转换结束时变量的最终值。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 GetFinalValue 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a> CInterpolatorBase：： InterpolateValue

按给定的偏移量内插值

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>parameters

*offset*<br/>
与转换开头之间的偏移量。 偏移量始终大于或等于零，并且小于转换的持续时间。 如果转换的持续时间为零，则不会调用此方法。

*value*<br/>
输出。 内插值。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 InterpolateValue 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a> CInterpolatorBase：： InterpolateVelocity

按给定的偏移量内插速度

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>parameters

*offset*<br/>
与转换开头之间的偏移量。 偏移量始终大于或等于零且小于或等于转换的持续时间。 如果转换的持续时间为零，则不会调用此方法。

*速度*<br/>
输出。 变量在偏移量处的速度。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 InterpolateVelocity 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a> CInterpolatorBase：： SetCustomInterpolator

存储一个指向自定义内插的指针，该指针将处理事件。

```cpp
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>parameters

*pInterpolator*<br/>
指向自定义内插的指针。

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a> CInterpolatorBase：： SetDuration

设置内插程序的持续时间

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 SetDuration 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> CInterpolatorBase：： SetInitialValueAndVelocity

设置内插程序的初始值和速度。

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>parameters

*initialValue*<br/>
转换开始时变量的值。

*initialVelocity*<br/>
变量在转换开始时的速度。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 如果未设置 CCustomInterpolator，或自定义实现从 SetInitialValueAndVelocity 方法返回 FALSE，则它将返回 E_FAIL。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
