---
description: 了解详细信息： CAnimationBaseObject 类
title: CAnimationBaseObject 类
ms.date: 03/27/2019
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: bc44d0e55b409f66648007eeb27fefd386640d9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318658"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject 类

所有动画对象的基类。

## <a name="syntax"></a>语法

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationBaseObject：： CAnimationBaseObject](#canimationbaseobject)|已重载。 构造动画对象。|
|[CAnimationBaseObject：： ~ CAnimationBaseObject](#_dtorcanimationbaseobject)|析构函数。 在销毁动画对象时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationBaseObject：： ApplyTransitions](#applytransitions)|将转换添加到带封装动画变量的情节提要。|
|[CAnimationBaseObject：： ClearTransitions](#cleartransitions)|删除所有相关转换。|
|[CAnimationBaseObject：： ContainsVariable](#containsvariable)|确定动画对象是否包含特定的动画变量。|
|[CAnimationBaseObject：： CreateTransitions](#createtransitions)|创建与动画对象关联的转换。|
|[CAnimationBaseObject：:D etachFromController](#detachfromcontroller)|从父动画控制器分离动画对象。|
|[CAnimationBaseObject：： EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|设置整数值更改事件处理程序。|
|[CAnimationBaseObject：： EnableValueChangedEvent](#enablevaluechangedevent)|设置值更改事件处理程序。|
|[CAnimationBaseObject：： GetAutodestroyTransitions](#getautodestroytransitions)|指示是否自动销毁相关转换。|
|[CAnimationBaseObject：： GetGroupID](#getgroupid)|返回当前组 ID。|
|[CAnimationBaseObject：： GetObjectID](#getobjectid)|返回当前对象 ID。|
|[CAnimationBaseObject：： GetUserData](#getuserdata)|返回用户定义数据。|
|[CAnimationBaseObject：： SetAutodestroyTransitions](#setautodestroytransitions)|设置标志以自动销毁转换。|
|[CAnimationBaseObject：： SetID](#setid)|设置新 Id。|
|[CAnimationBaseObject：： SetUserData](#setuserdata)|设置用户定义数据。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationBaseObject：： GetAnimationVariableList](#getanimationvariablelist)|收集指向包含的动画变量的指针。|
|[CAnimationBaseObject：： SetParentAnimationObjects](#setparentanimationobjects)|建立动画变量、包含在动画对象中的关系及其容器。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationBaseObject：： m_bAutodestroyTransitions](#m_bautodestroytransitions)|指定是否应自动销毁相关转换。|
|[CAnimationBaseObject：： m_dwUserData](#m_dwuserdata)|存储用户定义数据。|
|[CAnimationBaseObject：： m_nGroupID](#m_ngroupid)|指定动画对象的组 ID。|
|[CAnimationBaseObject：： m_nObjectID](#m_nobjectid)|指定动画对象的对象 ID。|
|[CAnimationBaseObject：： m_pParentController](#m_pparentcontroller)|指向父动画控制器的指针。|

## <a name="remarks"></a>备注

此类实现所有动画对象的基本方法。 动画对象可以表示应用程序中的值、点、大小、矩形或颜色以及任何自定义实体。 动画对象存储在动画组中 (参阅 CAnimationGroup) 。 每个组可以单独进行动画处理，并可被视为情节提要的模拟。 动画对象封装一个或多个动画变量 (参阅 CAnimationVariable) ，具体取决于其逻辑表示形式。 例如，CAnimationRect 包含四个动画变量-每个矩形边有一个变量。 每个动画对象类都公开重载的 AddTransition 方法，该方法应用于将转换应用于封装的动画变量。 动画对象可以通过对象 ID 进行标识 (可以选择) 和组 ID。 若要将某个动画对象置于正确的组，需要组 ID，但如果未指定组 ID，则会将一个对象放置在 ID 为0的默认组中。 如果使用不同的 GroupID 调用 SetID，则会将动画对象移到另一个组 (如有必要) 会创建一个新组。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a> CAnimationBaseObject：： ~ CAnimationBaseObject

析构函数。 在销毁动画对象时调用。

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a> CAnimationBaseObject：： ApplyTransitions

将转换添加到带封装动画变量的情节提要。

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要的指针。

*bDependOnKeyframes*<br/>
为 FALSE 时，此方法仅添加不依赖于关键帧的转换。

### <a name="return-value"></a>返回值

如果成功添加了转换，则为 TRUE。

### <a name="remarks"></a>备注

向情节提要添加了已使用 (AddTransition 在派生类) 派生类中添加的相关转换。

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a> CAnimationBaseObject：： CAnimationBaseObject

构造动画对象。

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*nGroupID*<br/>
指定组 ID。

*nObjectID*<br/>
指定对象 ID。

*dwUserData*<br/>
用户定义的数据，可与动画对象相关联，稍后在运行时检索。

### <a name="remarks"></a>备注

构造动画对象，并将默认对象 ID (0) 和组 ID 指定 (0) 。

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a> CAnimationBaseObject：： ClearTransitions

删除所有相关转换。

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>parameters

*bAutodestroy*<br/>
指定是否自动销毁转换对象，或只是将其从相关列表中移除。

### <a name="remarks"></a>备注

如果 bAutodestroy 或 m_bAutodestroyTransitions 标志为 TRUE，则删除所有相关转换并销毁它们。 仅当未在堆栈上分配转换时，才应自动销毁转换。 如果上述标志为 FALSE，则只会从相关转换的内部列表中删除转换。

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a> CAnimationBaseObject：： ContainsVariable

确定动画对象是否包含特定的动画变量。

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>parameters

*pVariable*<br/>
指向动画变量的指针。

### <a name="return-value"></a>返回值

如果动画变量包含在动画对象中，则为 TRUE; 否则为。否则为 FALSE。

### <a name="remarks"></a>备注

此方法可用于确定 pVariable 指定的动画变量是否包含在动画对象中。 动画对象（取决于其类型）可能包含多个动画变量。 例如，CAnimationColor 包含三个变量，每个颜色组件 (红、绿和蓝) 。 当动画变量值更改时，Windows 动画 API 将发送 ValueChanged 或 IntegerValueChanged 事件 (如果启用) ，则此事件的参数是指向动画变量的接口 IUIAnimationVariable 的指针。 此方法可帮助获取指向包含 COM 对象的指针的动画指针。

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a> CAnimationBaseObject：： CreateTransitions

创建与动画对象关联的转换。

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>返回值

如果成功创建了转换，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

循环遍历派生动画对象中封装的动画变量列表，并创建与每个动画变量关联的转换。

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a> CAnimationBaseObject：:D etachFromController

从父动画控制器分离动画对象。

```cpp
void DetachFromController();
```

### <a name="remarks"></a>备注

此方法在内部使用。

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a> CAnimationBaseObject：： EnableIntegerValueChangedEvent

设置整数值更改事件处理程序。

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>parameters

*pController*<br/>
指向父控制器的指针。

*bEnable*<br/>
指定是启用还是禁用整数值更改事件。

### <a name="remarks"></a>备注

如果已启用整数值更改事件处理程序，则可以在 CAnimationController：： OnAnimationIntegerValueChanged 方法中处理此事件，该方法应在 CAnimationController 派生的类中重写。 每次动画整数值发生更改时，都会调用此方法。

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a> CAnimationBaseObject：： EnableValueChangedEvent

设置值更改事件处理程序。

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>parameters

*pController*<br/>
指向父控制器的指针。

*bEnable*<br/>
指定是启用还是禁用值更改事件。

### <a name="remarks"></a>备注

如果已启用值更改事件处理程序，则可以在 CAnimationController：： OnAnimationValueChanged 方法中处理此事件，该方法应在 CAnimationController 派生的类中重写。 每次动画值发生更改时，都会调用此方法。

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationBaseObject：： GetAnimationVariableList

收集指向包含的动画变量的指针。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>parameters

*list*<br/>
必须使用动画对象中包含的动画变量填充的列表。

### <a name="remarks"></a>备注

必须在派生类中重写此纯虚方法。 动画对象（取决于其类型）包含一个或多个动画变量。 例如，CAnimationPoint 包含两个变量，分别用于 X 和 Y 坐标。 基类 CAnimationBaseObject 实现了一些泛型方法，这些方法作用于动画变量列表： ApplyTransitions、ClearTransitions、EnableValueChangedEvent、EnableIntegerValueChangedEvent。 这些方法调用 GetAnimationVariableList，该派生类中填充了特定动画对象中包含的实际动画变量，然后循环切换列表并执行必要的操作。 如果创建自定义动画对象，则必须添加以 *列出* 该对象中包含的所有动画变量。

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a> CAnimationBaseObject：： GetAutodestroyTransitions

指示是否自动销毁相关转换。

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>返回值

如果为 TRUE，则将自动销毁相关的转换;如果为 FALSE，则应通过调用应用程序释放转换对象。

### <a name="remarks"></a>备注

默认情况下，此标志为 TRUE。 仅当在堆栈上分配了转换，并且/或转换应被调用应用程序释放时，才设置此标志。

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a> CAnimationBaseObject：： GetGroupID

返回当前组 ID。

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>返回值

当前组 ID。

### <a name="remarks"></a>备注

使用此方法可检索组 ID。 如果未在构造函数中显式设置组 ID 或将组 ID 设置为 SetID，则为0。

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a> CAnimationBaseObject：： GetObjectID

返回当前对象 ID。

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>返回值

当前对象 ID。

### <a name="remarks"></a>备注

使用此方法可检索对象 ID。 如果未在构造函数中或通过 SetID 显式设置对象 ID，则为0。

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a> CAnimationBaseObject：： GetUserData

返回用户定义数据。

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>返回值

自定义数据的值。

### <a name="remarks"></a>备注

调用此方法可在运行时检索自定义数据。 如果未在构造函数或 with SetUserData 中显式初始化，则返回值将为0。

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a> CAnimationBaseObject：： m_bAutodestroyTransitions

指定是否应自动销毁相关转换。

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a> CAnimationBaseObject：： m_dwUserData

存储用户定义数据。

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationBaseObject：： m_nGroupID

指定动画对象的组 ID。

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a> CAnimationBaseObject：： m_nObjectID

指定动画对象的对象 ID。

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationBaseObject：： m_pParentController

指向父动画控制器的指针。

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationBaseObject：： SetAutodestroyTransitions

设置标志以自动销毁转换。

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>parameters

*bValue*<br/>
指定自动销毁标志。

### <a name="remarks"></a>备注

仅当使用 new 运算符分配了转换对象时，才设置此标志。 如果由于某些原因导致转换对象在堆栈上分配，则自动销毁标志应为 FALSE。 默认情况下，此标志为 TRUE。

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a> CAnimationBaseObject：： SetID

设置新 Id。

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>parameters

*nObjectID*<br/>
指定新的对象 ID。

*nGroupID*<br/>
指定新的组 ID。

### <a name="remarks"></a>备注

允许更改对象 ID 和组 ID。 如果新的组 ID 不同于当前 ID，则会将动画对象移到另一个组 (创建新组（如有必要）) 。

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a> CAnimationBaseObject：： SetParentAnimationObjects

建立动画变量、包含在动画对象中的关系及其容器。

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>备注

此帮助器可用于建立动画对象中包含的动画变量与其容器之间的关系。 它循环使用动画变量，并将向后指针设置到每个动画变量的父动画对象。 在当前实现中，将在 CAnimationBaseObject：： ApplyTransitions 中建立实际关系，因此，在调用 CAnimationGroup：：动画之前，不会设置 back 指针。 在处理事件时，知道关系可能会很有帮助，并需要从 CAnimationVariable 获取父动画对象。 使用 CAnimationVariable：： GetParentAnimationObject。

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a> CAnimationBaseObject：： SetUserData

设置用户定义数据。

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>parameters

*dwUserData*<br/>
指定自定义数据。

### <a name="remarks"></a>备注

使用此方法可将自定义数据与动画对象相关联。 此数据稍后可通过 GetUserData 在运行时检索。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
