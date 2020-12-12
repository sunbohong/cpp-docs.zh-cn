---
description: 了解详细信息： CBaseTransition 类
title: CBaseTransition 类
ms.date: 03/27/2019
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: 16a7b5e7f88e292fd2b771c627f7169c70fec2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122819"
---
# <a name="cbasetransition-class"></a>CBaseTransition 类

表示基本转换。

## <a name="syntax"></a>语法

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>成员

### <a name="public-enumerations"></a>公共枚举

|名称|描述|
|----------|-----------------|
|[CBaseTransition：： TRANSITION_TYPE 枚举](#transition_type_enumeration)|定义 Windows 动画 API 的 MFC 实现当前支持的转换类型。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CBaseTransition：： CBaseTransition](#cbasetransition)|构造基本转换对象。|
|[CBaseTransition：： ~ CBaseTransition](#_dtorcbasetransition)|析构函数。 当转换对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CBaseTransition：： AddToStoryboard](#addtostoryboard)|将过渡添加到情节提要。|
|[CBaseTransition：： AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|将过渡添加到情节提要。|
|[CBaseTransition：： Clear](#clear)|释放封装的 IUIAnimationTransition COM 对象。|
|[CBaseTransition：： Create](#create)|创建 COM 转换。|
|[CBaseTransition：： GetEndKeyframe](#getendkeyframe)|返回开始关键帧。|
|[CBaseTransition：： GetRelatedVariable](#getrelatedvariable)|返回指向相关变量的指针。|
|[CBaseTransition：： GetStartKeyframe](#getstartkeyframe)|返回开始关键帧。|
|[CBaseTransition：： GetTransition](#gettransition)|已重载。 返回指向基础 COM 转换对象的指针。|
|[CBaseTransition：： GetType](#gettype)|返回过渡类型。|
|[CBaseTransition：： IsAdded](#isadded)|指示是否已将转换添加到情节提要。|
|[CBaseTransition：： SetKeyframes](#setkeyframes)|为转换设置关键帧。|
|[CBaseTransition：： SetRelatedVariable](#setrelatedvariable)|在动画变量和转换之间建立关系。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CBaseTransition：： m_bAdded](#m_badded)|指定是否已将转换添加到情节提要。|
|[CBaseTransition：： m_pEndKeyframe](#m_pendkeyframe)|存储指向指定转换结束的关键帧的指针。|
|[CBaseTransition：： m_pRelatedVariable](#m_prelatedvariable)|指向动画变量的指针，该变量使用存储在 m_transition 中的转换进行动画处理。|
|[CBaseTransition：： m_pStartKeyframe](#m_pstartkeyframe)|存储指向指定转换开始的关键帧的指针。|
|[CBaseTransition：： m_transition](#m_transition)|存储指向 IUIAnimationTransition 的指针。 如果尚未创建 COM 转换对象，则为 NULL。|
|[CBaseTransition：： m_type](#m_type)|存储转换类型。|

## <a name="remarks"></a>备注

此类封装 IUIAnimationTransition 接口，并充当所有转换的基类。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a> CBaseTransition：： ~ CBaseTransition

析构函数。 当转换对象被销毁时调用。

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseTransition：： AddToStoryboard

将过渡添加到情节提要。

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要的指针，它将对相关变量进行动画处理。

### <a name="return-value"></a>返回值

如果已成功将转换添加到情节提要，则为 TRUE。

### <a name="remarks"></a>备注

将转换应用于情节提要中的相关变量。 如果这是在此情节提要中应用于此变量的第一个转换，则从情节提要的开头开始转换。 否则，转换将追加到最近添加到变量中的转换。

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a> CBaseTransition：： AddToStoryboardAtKeyframes

将过渡添加到情节提要。

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要的指针，它将对相关变量进行动画处理。

### <a name="return-value"></a>返回值

如果已成功将转换添加到情节提要，则为 TRUE。

### <a name="remarks"></a>备注

将转换应用于情节提要中的相关变量。 如果指定了开始关键帧，则从该关键帧开始转换。 如果指定了结束关键帧，转换将从开始关键帧开始，并在结束关键帧处停止。 如果转换是使用指定的 duration 参数创建的，则会在开始和结束关键帧之间的持续时间内覆盖该持续时间。 如果未指定关键帧，则转换将追加到最近添加到变量的转换。

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a> CBaseTransition：： CBaseTransition

构造基本转换对象。

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a> CBaseTransition：： Clear

释放封装的 IUIAnimationTransition COM 对象。

```cpp
void Clear();
```

### <a name="remarks"></a>备注

应从派生类的 Create 方法中调用此方法，以防止 IUITransition 接口泄漏。

## <a name="cbasetransitioncreate"></a><a name="create"></a> CBaseTransition：： Create

创建 COM 转换。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>parameters

*pLibrary*<br/>
指向转换库的指针，用于创建标准转换。 对于自定义转换，此值可以为 NULL。

*pFactory*<br/>
一个指向转换工厂的指针，该指针创建自定义转换。 对于标准转换，此值可以为 NULL。

### <a name="return-value"></a>返回值

如果已成功创建转换 COM 对象，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

这是一个纯虚函数，必须在派生类中进行重写。 它由框架调用，用于实例化基础 COM 转换对象。

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a> CBaseTransition：： GetEndKeyframe

返回开始关键帧。

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>返回值

指向关键帧的有效指针，如果不应在关键帧之间插入转换，则为 NULL。

### <a name="remarks"></a>备注

此方法可用于访问之前由 SetKeyframes 设置的关键帧对象。 在将转换添加到情节提要时，顶级代码会调用此方法。

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a> CBaseTransition：： GetRelatedVariable

返回指向相关变量的指针。

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>返回值

指向动画变量的有效指针，如果 SetRelatedVariable 未设置动画变量，则为 NULL。

### <a name="remarks"></a>备注

这是对相关动画变量的访问器。

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a> CBaseTransition：： GetStartKeyframe

返回开始关键帧。

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>返回值

指向关键帧的有效指针，如果不应在关键帧后开始转换，则为 NULL。

### <a name="remarks"></a>备注

此方法可用于访问之前由 SetKeyframes 设置的关键帧对象。 在将转换添加到情节提要时，顶级代码会调用此方法。

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a> CBaseTransition：： GetTransition

返回指向基础 COM 转换对象的指针。

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>parameters

*pLibrary*<br/>
指向转换库的指针，用于创建标准转换。 对于自定义转换，此值可以为 NULL。

*pFactory*<br/>
一个指向转换工厂的指针，该指针创建自定义转换。 对于标准转换，此值可以为 NULL。

### <a name="return-value"></a>返回值

如果无法创建基础转换，则为指向 IUIAnimationTransition 的有效指针或 NULL。

### <a name="remarks"></a>备注

此方法返回指向基础 COM 转换对象的指针，并在必要时创建该指针。

## <a name="cbasetransitiongettype"></a><a name="gettype"></a> CBaseTransition：： GetType

返回过渡类型。

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>返回值

TRANSITION_TYPE 枚举值之一。

### <a name="remarks"></a>备注

此方法可用于按类型标识转换对象。 该类型是在派生类的构造函数中设置的。

## <a name="cbasetransitionisadded"></a><a name="isadded"></a> CBaseTransition：： IsAdded

指示是否已将转换添加到情节提要。

```
BOOL IsAdded();
```

### <a name="return-value"></a>返回值

如果已将转换添加到情节提要，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

当顶级代码将转换添加到情节提要时，将在内部设置此标志。

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a> CBaseTransition：： m_bAdded

指定是否已将转换添加到情节提要。

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a> CBaseTransition：： m_pEndKeyframe

存储指向指定转换结束的关键帧的指针。

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a> CBaseTransition：： m_pRelatedVariable

指向动画变量的指针，该变量使用存储在 m_transition 中的转换进行动画处理。

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a> CBaseTransition：： m_pStartKeyframe

存储指向指定转换开始的关键帧的指针。

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a> CBaseTransition：： m_transition

存储指向 IUIAnimationTransition 的指针。 如果尚未创建 COM 转换对象，则为 NULL。

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a> CBaseTransition：： m_type

存储转换类型。

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a> CBaseTransition：： SetKeyframes

为转换设置关键帧。

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>parameters

*pStart*<br/>
指定转换开始的关键帧。

*挂起*<br/>
指定转换结束的关键帧。

### <a name="remarks"></a>备注

此方法告知转换在指定关键帧后开始，并在指定关键帧之前结束时（可选），如果挂起不为 NULL，则为。 如果转换是使用指定的 duration 参数创建的，则会在开始和结束关键帧之间的持续时间内覆盖该持续时间。

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a> CBaseTransition：： SetRelatedVariable

在动画变量和转换之间建立关系。

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>parameters

*pVariable*<br/>
指向相关动画变量的指针。

### <a name="remarks"></a>备注

在动画变量和转换之间建立关系。 转换只能应用于一个变量。

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a> CBaseTransition：： TRANSITION_TYPE 枚举

定义 Windows 动画 API 的 MFC 实现当前支持的转换类型。

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>备注

转换类型在特定转换的构造函数中设置。 例如，CSinusoidalTransitionFromRange 将其类型设置为 SINUSOIDAL_FROM_RANGE。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
