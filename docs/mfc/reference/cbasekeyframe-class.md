---
description: 了解详细信息： CBaseKeyFrame 类
title: CBaseKeyFrame 类
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: 0bebd91183eab9be71e8df4928dc621565718cb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261251"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame 类

实现关键帧的基本功能。

## <a name="syntax"></a>语法

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CBaseKeyFrame：： CBaseKeyFrame](#cbasekeyframe)|构造关键帧对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CBaseKeyFrame：： AddToStoryboard](#addtostoryboard)|向情节提要添加关键帧。|
|[CBaseKeyFrame：： GetAnimationKeyframe](#getanimationkeyframe)|返回基础关键帧值。|
|[CBaseKeyFrame：： IsAdded](#isadded)|指示是否已将关键帧添加到情节提要。|
|[CBaseKeyFrame：： IsKeyframeAtOffset](#iskeyframeatoffset)|指定是否应将关键帧添加到偏移或转换后的情节提要。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CBaseKeyFrame：： m_bAdded](#m_badded)|指定是否已将此关键帧添加到情节提要。|
|[CBaseKeyFrame：： m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|指定是否应将此关键帧添加到来自另一现有关键帧的偏移，或在某个转换结束时添加到情节提要。|
|[CBaseKeyFrame：： m_keyframe](#m_keyframe)|表示 Windows 动画 API 关键帧。 如果未初始化某个关键帧，则会将其设置为预定义的值 UI_ANIMATION_KEYFRAME_STORYBOARD_START。|

## <a name="remarks"></a>备注

封装 UI_ANIMATION_KEYFRAME 变量。 用作任何关键帧实现的基类。 关键帧表示情节提要中的时间点，可用于指定转换的开始时间和结束时间。 有两种类型的关键帧-添加到情节提要的关键帧，按指定的偏移量 (时间) ，或在指定的转换后添加的关键帧。 由于某些转换的持续时间在动画开始之前无法知道，某些关键帧的实际值仅在运行时确定。 由于关键帧可能依赖于转换，而后者又依赖于关键帧，因此在生成关键帧链时防止无限递归非常重要。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseKeyFrame：： AddToStoryboard

向情节提要添加关键帧。

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要的指针。

*bDeepAdd*<br/>
如果此参数为 TRUE，并且要添加的关键帧依赖于其他某个关键帧或转换，则此方法会先尝试将此关键帧或过渡添加到情节提要。

### <a name="return-value"></a>返回值

如果成功将关键帧添加到情节提要，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此方法可向情节提要添加关键帧。

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a> CBaseKeyFrame：： CBaseKeyFrame

构造关键帧对象。

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a> CBaseKeyFrame：： GetAnimationKeyframe

返回基础关键帧值。

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>返回值

当前关键帧。 默认值为 UI_ANIMATION_KEYFRAME_STORYBOARD_START。

### <a name="remarks"></a>备注

这是对基础关键帧值的访问器。

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a> CBaseKeyFrame：： IsAdded

指示是否已将关键帧添加到情节提要。

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>返回值

如果向情节提要添加关键帧，则为 TRUE;否则 FALSE。

### <a name="remarks"></a>备注

在基类 IsAdded 中，始终返回 TRUE，但在派生类中被重写。

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a> CBaseKeyFrame：： IsKeyframeAtOffset

指定是否应将关键帧添加到偏移或转换后的情节提要。

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>返回值

如果应按一定偏移量将关键帧添加到情节提要，则为 TRUE。 如果在某些转换后应将关键帧添加到情节提要，则为 FALSE。

### <a name="remarks"></a>备注

指定是否应将关键帧添加到偏移量处的情节提要。 必须在派生类中指定偏移或转换。

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a> CBaseKeyFrame：： m_bAdded

指定是否已将此关键帧添加到情节提要。

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a> CBaseKeyFrame：： m_bIsKeyframeAtOffset

指定是否应将此关键帧添加到来自另一现有关键帧的偏移，或在某个转换结束时添加到情节提要。

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a> CBaseKeyFrame：： m_keyframe

表示 Windows 动画 API 关键帧。 如果未初始化某个关键帧，则会将其设置为预定义的值 UI_ANIMATION_KEYFRAME_STORYBOARD_START。

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
