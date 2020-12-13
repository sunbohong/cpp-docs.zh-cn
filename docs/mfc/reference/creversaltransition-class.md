---
description: 了解详细信息： CReversalTransition 类
title: CReversalTransition 类
ms.date: 11/04/2016
f1_keywords:
- CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::Create
- AFXANIMATIONCONTROLLER/CReversalTransition::m_duration
helpviewer_keywords:
- CReversalTransition [MFC], CReversalTransition
- CReversalTransition [MFC], Create
- CReversalTransition [MFC], m_duration
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
ms.openlocfilehash: f1d16562751e93ccf6df7ca3f70dac08bda8423d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343002"
---
# <a name="creversaltransition-class"></a>CReversalTransition 类

封装反向转换。

## <a name="syntax"></a>语法

```
class CReversalTransition : public CBaseTransition;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CReversalTransition：： CReversalTransition](#creversaltransition)|构造一个反转转换对象并初始化该对象的持续时间。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CReversalTransition：： Create](#create)|调用转换库以创建封装的转换 COM 对象。  (重写 [CBaseTransition：： Create](../../mfc/reference/cbasetransition-class.md#create). ) |

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CReversalTransition：： m_duration](#m_duration)|转换的持续时间。|

## <a name="remarks"></a>备注

反向转换在给定持续时间内平滑更改方向。 最终值将与初始值相同，最终速度将为起始速度的负值。 由于所有转换都将自动清除，因此建议使用 operator new 将其分配给它们。 封装的 IUIAnimationTransition COM 对象由 CAnimationController：： AnimateGroup 创建，直到它为 NULL。 在创建此 COM 对象之后更改成员变量不起作用。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CReversalTransition](../../mfc/reference/creversaltransition-class.md)

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="creversaltransitioncreate"></a><a name="create"></a> CReversalTransition：： Create

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

## <a name="creversaltransitioncreversaltransition"></a><a name="creversaltransition"></a> CReversalTransition：： CReversalTransition

构造一个反转转换对象并初始化该对象的持续时间。

```
CReversalTransition(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>parameters

*duration*<br/>
转换的持续时间。

## <a name="creversaltransitionm_duration"></a><a name="m_duration"></a> CReversalTransition：： m_duration

转换的持续时间。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
