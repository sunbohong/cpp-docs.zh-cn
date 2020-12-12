---
description: 了解详细信息： CParabolicTransitionFromAcceleration 类
title: CParabolicTransitionFromAcceleration 类
ms.date: 11/04/2016
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
ms.openlocfilehash: 037c2ff8391b655c556339547966b14ee094fee0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301485"
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration 类

封装抛物线加速转换。

## <a name="syntax"></a>语法

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration：： CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|构造抛物线转换，并使用指定的参数对其进行初始化。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration：： Create](#create)|调用转换库以创建封装的转换 COM 对象。  (重写 [CBaseTransition：： Create](../../mfc/reference/cbasetransition-class.md#create). ) |

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration：： m_dblAcceleration](#m_dblacceleration)|转换过程中动画变量的加速。|
|[CParabolicTransitionFromAcceleration：： m_dblFinalValue](#m_dblfinalvalue)|转换结束时动画变量的值。|
|[CParabolicTransitionFromAcceleration：： m_dblFinalVelocity](#m_dblfinalvelocity)|动画变量在转换结束时的速度。|

## <a name="remarks"></a>备注

在抛物线加速转换期间，动画变量的值将从初始值更改为以指定速度结束的最终值。 您可以通过指定加速速度来控制变量到达最终值的速度。 由于所有转换都将自动清除，因此建议使用 operator new 将其分配给它们。 封装的 IUIAnimationTransition COM 对象由 CAnimationController：： AnimateGroup 创建，直到它为 NULL。 在创建此 COM 对象之后更改成员变量不起作用。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="cparabolictransitionfromaccelerationcparabolictransitionfromacceleration"></a><a name="cparabolictransitionfromacceleration"></a> CParabolicTransitionFromAcceleration：： CParabolicTransitionFromAcceleration

构造抛物线转换，并使用指定的参数对其进行初始化。

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>parameters

*dblFinalValue*<br/>
转换结束时动画变量的值。

*dblFinalVelocity*<br/>
动画变量在转换结束时的速度。

*dblAcceleration*<br/>
转换过程中动画变量的加速。

## <a name="cparabolictransitionfromaccelerationcreate"></a><a name="create"></a> CParabolicTransitionFromAcceleration：： Create

调用转换库以创建封装的转换 COM 对象。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>parameters

*pLibrary*<br/>
指向转换库的指针，它负责创建标准转换。

### <a name="return-value"></a>返回值

如果成功创建转换，则为 TRUE;否则为 FALSE。

## <a name="cparabolictransitionfromaccelerationm_dblacceleration"></a><a name="m_dblacceleration"></a> CParabolicTransitionFromAcceleration：： m_dblAcceleration

转换过程中动画变量的加速。

```
DOUBLE m_dblAcceleration;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> CParabolicTransitionFromAcceleration：： m_dblFinalValue

转换结束时动画变量的值。

```
DOUBLE m_dblFinalValue;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a> CParabolicTransitionFromAcceleration：： m_dblFinalVelocity

动画变量在转换结束时的速度。

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
