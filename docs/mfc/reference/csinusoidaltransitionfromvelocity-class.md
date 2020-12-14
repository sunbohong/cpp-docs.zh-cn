---
description: 了解详细信息： CSinusoidalTransitionFromVelocity 类
title: CSinusoidalTransitionFromVelocity 类
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
ms.openlocfilehash: 96f4a4c6343f3635f3b60480f49c5af6e6f1e089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342749"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity 类

封装其幅度由动画变量的初始速度决定的正弦速度转换。

## <a name="syntax"></a>语法

```
class CSinusoidalTransitionFromVelocity : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity：： CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|构造转换对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity：： Create](#create)|调用转换库以创建封装的转换 COM 对象。  (重写 [CBaseTransition：： Create](../../mfc/reference/cbasetransition-class.md#create). ) |

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity：： m_duration](#m_duration)|转换的持续时间。|
|[CSinusoidalTransitionFromVelocity：： m_period](#m_period)|正弦波的振荡时间（秒）。|

## <a name="remarks"></a>备注

动画变量的值振荡正弦范围转换的整个持续时间内的初始值。 在转换开始时，振荡的幅度由动画变量的速度决定。 由于所有转换都将自动清除，因此建议使用 operator new 将其分配给它们。 封装的 IUIAnimationTransition COM 对象由 CAnimationController：： AnimateGroup 创建，直到它为 NULL。 在创建此 COM 对象之后更改成员变量不起作用。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromvelocitycreate"></a><a name="create"></a> CSinusoidalTransitionFromVelocity：： Create

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

## <a name="csinusoidaltransitionfromvelocitycsinusoidaltransitionfromvelocity"></a><a name="csinusoidaltransitionfromvelocity"></a> CSinusoidalTransitionFromVelocity：： CSinusoidalTransitionFromVelocity

构造转换对象。

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

*同期*<br/>
正弦波的振荡时间（秒）。

## <a name="csinusoidaltransitionfromvelocitym_duration"></a><a name="m_duration"></a> CSinusoidalTransitionFromVelocity：： m_duration

转换的持续时间。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromvelocitym_period"></a><a name="m_period"></a> CSinusoidalTransitionFromVelocity：： m_period

正弦波的振荡时间（秒）。

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
