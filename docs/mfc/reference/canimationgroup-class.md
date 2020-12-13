---
description: 了解详细信息： CAnimationGroup 类
title: CAnimationGroup 类
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 45fd49b95f73811f52795b87bf3de2dd004fa5ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336799"
---
# <a name="canimationgroup-class"></a>CAnimationGroup 类

实现一个动画组，该动画组组合动画情节提要、动画对象和转换以定义动画。

## <a name="syntax"></a>语法

```
class CAnimationGroup;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationGroup：： CAnimationGroup](#canimationgroup)|构造动画组。|
|[CAnimationGroup：： ~ CAnimationGroup](#_dtorcanimationgroup)|析构函数。 当动画组被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationGroup：：动画](#animate)|对组进行动画处理。|
|[CAnimationGroup：： ApplyTransitions](#applytransitions)|将转换应用于动画对象。|
|[CAnimationGroup：： FindAnimationObject](#findanimationobject)|查找包含指定动画变量的动画对象。|
|[CAnimationGroup：： GetGroupID](#getgroupid)|返回 GroupID。|
|[CAnimationGroup：： RemoveKeyframes](#removekeyframes)|删除和（可选）销毁属于动画组的所有关键帧。|
|[CAnimationGroup：： RemoveTransitions](#removetransitions)|从属于动画组的动画对象中移除转换。|
|[CAnimationGroup：： Schedule](#schedule)|在指定的时间安排动画。|
|[CAnimationGroup：： SetAutodestroyTransitions](#setautodestroytransitions)|指示属于组的所有动画对象自动销毁转换。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationGroup：： AddKeyframes](#addkeyframes)|向情节提要添加关键帧的帮助器。|
|[CAnimationGroup：： AddTransitions](#addtransitions)|向情节提要添加转换的帮助器。|
|[CAnimationGroup：： CreateTransitions](#createtransitions)|创建 COM 转换对象的帮助器。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationGroup：： m_bAutoclearTransitions](#m_bautocleartransitions)|指定如何清除属于组的动画对象的转换。 如果此成员为 TRUE，则在计划动画时将自动删除转换。 否则，您需要手动删除转换。|
|[CAnimationGroup：： m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|指定如何销毁动画对象。 如果此参数为 TRUE，则销毁组后，动画对象将自动销毁。 否则，必须手动销毁动画对象。 默认值是 FALSE。 仅当属于组的所有动画对象都是动态分配的 new 运算符时，才将此值设置为 TRUE。|
|[CAnimationGroup：： m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|指定如何销毁关键帧。 如果此值为 TRUE，则删除并销毁所有关键帧;否则，只会从列表中删除它们。 默认值为 TRUE。|
|[CAnimationGroup：： m_lstAnimationObjects](#m_lstanimationobjects)|包含动画对象的列表。|
|[CAnimationGroup：： m_lstKeyFrames](#m_lstkeyframes)|包含关键帧的列表。|
|[CAnimationGroup：： m_pStoryboard](#m_pstoryboard)|指向动画情节提要。 此指针仅在对动画调用后有效。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationGroup：： m_nGroupID](#m_ngroupid)|动画组的唯一标识符。|
|[CAnimationGroup：： m_pParentController](#m_pparentcontroller)|指向此组所属的动画控制器的指针。|

## <a name="remarks"></a>备注

动画组是使用 CAnimationController：： AddAnimationObject 添加动画对象时，动画控制器 (CAnimationController) 自动创建的。 动画组由 GroupID 标识，此操作通常作为参数来操作动画组。 GroupID 取自要添加到新动画组的第一个动画对象。 封装的动画情节提要是在调用 CAnimationController：： AnimateGroup 之后创建的，并且可以通过公共成员 m_pStoryboard 访问。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CAnimationGroup`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a> CAnimationGroup：： ~ CAnimationGroup

析构函数。 当动画组被销毁时调用。

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a> CAnimationGroup：： AddKeyframes

向情节提要添加关键帧的帮助器。

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要 COM 对象的指针。

*bAddDeep*<br/>
指定此方法是否应添加依赖于其他关键帧的情节提要关键帧。

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a> CAnimationGroup：： AddTransitions

向情节提要添加转换的帮助器。

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要 COM 对象的指针。

*bDependOnKeyframes*

## <a name="canimationgroupanimate"></a><a name="animate"></a> CAnimationGroup：：动画

对组进行动画处理。

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>parameters

*pManager*<br/>
*pTimer* 
*bScheduleNow*

### <a name="return-value"></a>返回值

如果该方法成功，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

此方法创建一个内部情节提要，创建和应用转换，并在 bScheduleNow 为 TRUE 时计划动画。 如果 bScheduleNow 为 FALSE，则需要调用计划以在指定的时间启动动画。

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a> CAnimationGroup：： ApplyTransitions

将转换应用于动画对象。

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>备注

如果尚未创建情节提要，此方法将断言处于调试模式。 它首先创建所有转换，然后将依赖于) 偏移量的 "静态" 关键帧添加 (关键帧，添加不依赖于关键帧的转换，根据转换和其他关键帧添加关键帧，并在最后添加依赖于关键帧的转换。

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a> CAnimationGroup：： CAnimationGroup

构造动画组。

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>parameters

*pParentController*<br/>
指向创建组的动画控制器的指针。

*nGroupID*<br/>
指定 GroupID。

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a> CAnimationGroup：： CreateTransitions

创建 COM 转换对象的帮助器。

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>返回值

如果方法成功，则为 TRUE; 否则为 FALSE。

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a> CAnimationGroup：： FindAnimationObject

查找包含指定动画变量的动画对象。

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>parameters

*pVariable*<br/>
指向动画变量的指针。

### <a name="return-value"></a>返回值

指向动画对象的指针; 如果找不到动画对象，则为 NULL。

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a> CAnimationGroup：： GetGroupID

返回 GroupID。

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>返回值

组标识符。

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a> CAnimationGroup：： m_bAutoclearTransitions

指定如何清除属于组的动画对象的转换。 如果此成员为 TRUE，则在计划动画时将自动删除转换。 否则，您需要手动删除转换。

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a> CAnimationGroup：： m_bAutodestroyAnimationObjects

指定如何销毁动画对象。 如果此参数为 TRUE，则销毁组后，动画对象将自动销毁。 否则，必须手动销毁动画对象。 默认值是 FALSE。 仅当属于组的所有动画对象都是动态分配的 new 运算符时，才将此值设置为 TRUE。

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a> CAnimationGroup：： m_bAutodestroyKeyframes

指定如何销毁关键帧。 如果此值为 TRUE，则删除并销毁所有关键帧;否则，只会从列表中删除它们。 默认值为 TRUE。

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a> CAnimationGroup：： m_lstAnimationObjects

包含动画对象的列表。

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a> CAnimationGroup：： m_lstKeyFrames

包含关键帧的列表。

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationGroup：： m_nGroupID

动画组的唯一标识符。

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationGroup：： m_pParentController

指向此组所属的动画控制器的指针。

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a> CAnimationGroup：： m_pStoryboard

指向动画情节提要。 此指针仅在对动画调用后有效。

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a> CAnimationGroup：： RemoveKeyframes

删除和（可选）销毁属于动画组的所有关键帧。

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>备注

如果 m_bAutodestroyKeyframes 成员为 TRUE，则将删除和销毁关键帧，否则仅从关键帧的内部列表中删除关键帧。

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a> CAnimationGroup：： RemoveTransitions

从属于动画组的动画对象中移除转换。

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>备注

如果 m_bAutoclearTransitions 标志设置为 TRUE，则此方法将循环遍历属于该组的所有动画对象，并调用 CAnimationObject：： ClearTransitions (FALSE) 。

## <a name="canimationgroupschedule"></a><a name="schedule"></a> CAnimationGroup：： Schedule

在指定的时间安排动画。

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>parameters

*pTimer*<br/>
指向动画计时器的指针。

*time*<br/>
指定安排动画的时间。

### <a name="return-value"></a>返回值

如果该方法成功，则为 TRUE;如果此方法失败，或者如果未在 bScheduleNow 设置为 FALSE 的情况调用动画，则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可在指定的时间计划动画。 必须先调用 bScheduleNow 设置为 FALSE 的动画。

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationGroup：： SetAutodestroyTransitions

指示属于组的所有动画对象自动销毁转换。

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*bAutoDestroy*<br/>
指定如何销毁转换。

### <a name="remarks"></a>备注

仅当在堆栈上分配转换时，才将此值设置为 FALSE。 默认值为 TRUE，因此强烈建议使用 new 运算符分配转换对象。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
