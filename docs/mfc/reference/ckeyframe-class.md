---
description: 了解详细信息： CKeyFrame 类
title: CKeyFrame 类
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: ec6aa45484965afbf0c636a1eed26a3d4a63e426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236875"
---
# <a name="ckeyframe-class"></a>CKeyFrame 类

表示动画关键帧。

## <a name="syntax"></a>语法

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CKeyFrame：： CKeyFrame](#ckeyframe)|已重载。 构造依赖于其他关键帧的关键帧。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CKeyFrame：： AddToStoryboard](#addtostoryboard)|向情节提要添加关键帧。  (重写 [CBaseKeyFrame：： AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard)。 ) |
|[CKeyFrame：： AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|在转换后向情节提要添加关键帧。|
|[CKeyFrame：： AddToStoryboardAtOffset](#addtostoryboardatoffset)|向情节提要添加偏移量处的关键帧。|
|[CKeyFrame：： GetExistingKeyframe](#getexistingkeyframe)|返回指向此关键帧所依赖的关键帧的指针。|
|[CKeyFrame：： GetOffset](#getoffset)|返回其他关键帧的偏移量。|
|[CKeyFrame：： GetTransition](#gettransition)|返回指向此关键帧所依赖的转换的指针。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CKeyFrame：： m_offset](#m_offset)|指定此关键帧与 m_pExistingKeyFrame 中存储的关键帧的偏移量。|
|[CKeyFrame：： m_pExistingKeyFrame](#m_pexistingkeyframe)|存储指向现有 keframe 的指针。 此关键帧添加到了与现有关键帧 m_offset 的情节提要中。|
|[CKeyFrame：： m_pTransition](#m_ptransition)|存储一个指向过渡的指针，该指针从该关键帧开始。|

## <a name="remarks"></a>备注

此类实现动画关键帧。 关键帧表示情节提要中的时间点，可用于指定转换的开始时间和结束时间。 关键帧可以基于其他关键帧，并) 其偏移 (（秒），也可以基于转换，表示此转换结束时的时间点。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CKeyFrame：： AddToStoryboard

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
指定是否以递归方式添加关键帧或过渡。

### <a name="return-value"></a>返回值

如果已成功添加关键帧，则为 TRUE。

### <a name="remarks"></a>备注

此方法将关键帧添加到情节提要。 如果它依赖于其他关键帧或转换并且 bDeepAdd 为 TRUE，则此方法尝试以递归方式添加它们。

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a> CKeyFrame：： AddToStoryboardAfterTransition

在转换后向情节提要添加关键帧。

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要的指针。

*bDeepAdd*<br/>
指定是否以递归方式添加转换。

### <a name="return-value"></a>返回值

如果已成功添加关键帧，则为 TRUE。

### <a name="remarks"></a>备注

此函数由框架调用，以在转换后向情节提要添加关键帧。

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a> CKeyFrame：： AddToStoryboardAtOffset

向情节提要添加偏移量处的关键帧。

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>parameters

*pStoryboard*<br/>
指向情节提要的指针。

*bDeepAdd*<br/>
指定是否添加此关键帧依赖于递归的关键帧。

### <a name="return-value"></a>返回值

如果已成功添加关键帧，则为 TRUE。

### <a name="remarks"></a>备注

此函数由框架调用，以将关键帧添加到偏移量处的情节提要。

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a> CKeyFrame：： CKeyFrame

构造依赖于转换的关键帧。

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>parameters

*pTransition*<br/>
指向转换的指针。

*pKeyframe*<br/>
指向关键帧的指针。

*offset*<br/>
PKeyframe 指定的关键帧的偏移量（以秒为单位）。

### <a name="remarks"></a>备注

在指定的转换结束时，构造的关键帧将表示情节提要中的时间点。

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a> CKeyFrame：： GetExistingKeyframe

返回指向此关键帧所依赖的关键帧的指针。

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>返回值

指向关键帧的有效指针，如果此关键帧不依赖于其他关键帧，则为 NULL。

### <a name="remarks"></a>备注

这是此关键帧所依赖的关键帧的访问器。

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a> CKeyFrame：： GetOffset

返回其他关键帧的偏移量。

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>返回值

相对于其他关键帧的偏移量（以秒为单位）。

### <a name="remarks"></a>备注

应调用此方法以确定从其他关键帧开始的偏移量（以秒为单位）。

## <a name="ckeyframegettransition"></a><a name="gettransition"></a> CKeyFrame：： GetTransition

返回指向此关键帧所依赖的转换的指针。

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>返回值

指向转换的有效指针; 如果此关键帧不依赖于转换，则为 NULL。

### <a name="remarks"></a>备注

这是对此关键帧依赖的转换的访问器。

## <a name="ckeyframem_offset"></a><a name="m_offset"></a> CKeyFrame：： m_offset

指定此关键帧与 m_pExistingKeyFrame 中存储的关键帧的偏移量。

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a> CKeyFrame：： m_pExistingKeyFrame

存储指向现有 keframe 的指针。 此关键帧添加到了与现有关键帧 m_offset 的情节提要中。

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a> CKeyFrame：： m_pTransition

存储一个指向过渡的指针，该指针从该关键帧开始。

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
