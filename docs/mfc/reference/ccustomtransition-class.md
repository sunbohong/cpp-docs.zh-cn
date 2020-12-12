---
description: 了解详细信息： CCustomTransition 类
title: CCustomTransition 类
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: 22c08cdcedc3a7cbdbe824ac1d98d62cfe810772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227658"
---
# <a name="ccustomtransition-class"></a>CCustomTransition 类

实现自定义转换。

## <a name="syntax"></a>语法

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CCustomTransition：： CCustomTransition](#ccustomtransition)|构造自定义转换对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CCustomTransition：： Create](#create)|调用转换库以创建封装的转换 COM 对象。  (重写 [CBaseTransition：： Create](../../mfc/reference/cbasetransition-class.md#create). ) |
|[CCustomTransition：： SetInitialValue](#setinitialvalue)|设置一个初始值，此值将应用于与此转换相关联的动画变量。|
|[CCustomTransition：： SetInitialVelocity](#setinitialvelocity)|设置要应用于与此过渡关联的动画变量的初始速度。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CCustomTransition：： m_bInitialValueSpecified](#m_binitialvaluespecified)|指定是否为初始值指定了 SetInitialValue。|
|[CCustomTransition：： m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|指定是否用 SetInitialVelocity 指定了初始速度。|
|[CCustomTransition：： m_initialValue](#m_initialvalue)|存储初始值。|
|[CCustomTransition：： m_initialVelocity](#m_initialvelocity)|存储初始速度。|
|[CCustomTransition：： m_pInterpolator](#m_pinterpolator)|存储指向自定义内插的指针。|

## <a name="remarks"></a>备注

CCustomTransitions 类允许开发人员实现自定义转换。 它创建并用作标准转换，但其构造函数接受指向自定义内插程序的指针作为参数。 执行以下步骤以使用自定义转换：1。 从 CCustomInterpolator 派生一个类，并至少实现 InterpolateValue 方法。 2. 确保自定义内插程序对象的生存期必须长于动画持续时间的时间。 3. 使用 operator new) CCustomTransition 对象实例化 (，并在构造函数中将指针传递到自定义内插。 4. 如果自定义内插需要这些参数，请调用 CCustomTransition：： SetInitialValue 和 CCustomTransition：： SetInitialVelocity。 5. 将指针传递到动画对象的 AddTransition 方法，其值应通过自定义算法进行动画处理。 6. 当动画对象的值更改时，Windows 动画 API 将调用 InterpolateValue (和其他相关方法) 在 CCustomInterpolator 中。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a> CCustomTransition：： CCustomTransition

构造自定义转换对象。

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>parameters

*pInterpolator*<br/>
指向自定义内插的指针。

## <a name="ccustomtransitioncreate"></a><a name="create"></a> CCustomTransition：： Create

调用转换库以创建封装的转换 COM 对象。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>parameters

*pFactory*<br/>
指向转换工厂的指针，它负责创建自定义转换。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

此方法还可以设置要应用于与此转换相关联的动画变量的初始值和初始速度。 出于此目的，必须先调用 SetInitialValue 和 SetInitialVelocity，然后框架才能创建封装的转换 COM 对象 (它在调用 CAnimationController：： AnimateGroup) 时发生。

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a> CCustomTransition：： m_bInitialValueSpecified

指定是否为初始值指定了 SetInitialValue。

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a> CCustomTransition：： m_bInitialVelocitySpecified

指定是否用 SetInitialVelocity 指定了初始速度。

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a> CCustomTransition：： m_initialValue

存储初始值。

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomTransition：： m_initialVelocity

存储初始速度。

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a> CCustomTransition：： m_pInterpolator

存储指向自定义内插的指针。

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a> CCustomTransition：： SetInitialValue

设置一个初始值，此值将应用于与此转换相关联的动画变量。

```cpp
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>parameters

*initialValue*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a> CCustomTransition：： SetInitialVelocity

设置要应用于与此过渡关联的动画变量的初始速度。

```cpp
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>parameters

*initialVelocity*

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
