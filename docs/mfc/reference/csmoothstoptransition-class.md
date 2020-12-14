---
description: 了解详细信息： CSmoothStopTransition 类
title: CSmoothStopTransition 类
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 14ea7475c886201d6b9b72eefc62f41679e73008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264526"
---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition 类

封装平稳停止转换。

## <a name="syntax"></a>语法

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSmoothStopTransition：： CSmoothStopTransition](#csmoothstoptransition)|构造一个平滑停止转换，并初始化其最大持续时间和最终值。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSmoothStopTransition：： Create](#create)|调用转换库以创建封装的转换 COM 对象。  (重写 [CBaseTransition：： Create](../../mfc/reference/cbasetransition-class.md#create). ) |

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CSmoothStopTransition：： m_dblFinalValue](#m_dblfinalvalue)|转换结束时动画变量的值。|
|[CSmoothStopTransition：： m_maximumDuration](#m_maximumduration)|转换的最大持续时间。|

## <a name="remarks"></a>备注

平滑停止转换在接近给定的最终值时减速，并达到速度为零的值。 转换的持续时间由初始速度、初始值和最终值之间的差异以及指定的最长持续时间决定。 如果没有包含一条抛物线弧的解决方案，则此方法将创建一个三次转换。 由于所有转换都将自动清除，因此建议使用 operator new 将其分配给它们。 封装的 IUIAnimationTransition COM 对象由 CAnimationController：： AnimateGroup 创建，直到它为 NULL。 在创建此 COM 对象之后更改成员变量不起作用。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="csmoothstoptransitioncreate"></a><a name="create"></a> CSmoothStopTransition：： Create

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

## <a name="csmoothstoptransitioncsmoothstoptransition"></a><a name="csmoothstoptransition"></a> CSmoothStopTransition：： CSmoothStopTransition

构造一个平滑停止转换，并初始化其最大持续时间和最终值。

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>parameters

*maximumDuration*<br/>
转换的最大持续时间。

*dblFinalValue*<br/>
转换结束时动画变量的值。

## <a name="csmoothstoptransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> CSmoothStopTransition：： m_dblFinalValue

转换结束时动画变量的值。

```
DOUBLE m_dblFinalValue;
```

## <a name="csmoothstoptransitionm_maximumduration"></a><a name="m_maximumduration"></a> CSmoothStopTransition：： m_maximumDuration

转换的最大持续时间。

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
