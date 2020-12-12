---
description: 了解详细信息： CMFCCaptionButton 类
title: CMFCCaptionButton 类
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 6c3c1cbeea4a548f2951276b3ad43cb598cf22a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327745"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton 类

`CMFCCaptionButton`类实现在停靠窗格或微型框架窗口的标题栏上显示的按钮。 通常，框架会自动创建标题按钮。

## <a name="syntax"></a>语法

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|名称|描述|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|构造 CMFCCaptionButton 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|返回由按钮表示的命令。|
|[CMFCCaptionButton::GetIconID](#geticonid)|返回与按钮关联的图像 ID。|
|[CMFCCaptionButton::GetRect](#getrect)|返回由按钮占据的矩形。|
|[CMFCCaptionButton：： GetSize](#getsize)|返回按钮的宽度和高度。|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|指示是否将标题栏高度设置为小尺寸。|
|[CMFCCaptionButton：： Move](#move)|设置按钮绘制位置和窗口显示状态。|
|[CMFCCaptionButton：： OnDraw](#ondraw)|绘制标题按钮。|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|设置标题栏的小尺寸。|

## <a name="remarks"></a>备注

您可以从 [CPaneFrameWnd 类](../../mfc/reference/cpaneframewnd-class.md) 派生一个类，并使用受保护的方法 `AddButton` 将标题按钮添加到袖珍框架窗口中。

CPaneFrameWnd 定义两种类型的标题按钮的命令 Id：

- AFX_CAPTION_BTN_PIN，当停靠窗格支持自动隐藏模式时，它将显示一个 PIN 按钮。

- AFX_CAPTION_BTN_CLOSE，它在窗格可以关闭或隐藏时显示 " **关闭** " 按钮。

## <a name="example"></a>示例

下面的示例演示如何构造 `CMFCCaptionButton` 对象并设置标题栏的迷你大小。

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>要求

**标头：** afxcaptionbutton

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a> CMFCCaptionButton::CMFCCaptionButton

构造 `CMFCCaptionButton` 对象。

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>parameters

*nHit*<br/>
中与按钮关联的命令。

*bLeftAlign*<br/>
中指定按钮是否与左侧对齐。

下表列出了 *nHit* 参数的可能值。

|值|命令|
|-----------|-------------|
|AFX_HTCLOSE|"关闭" 按钮。|
|HTMINBUTTON|最小化按钮。|
|HTMAXBUTTON|最大化按钮。|
|AFX_HTLEFTBUTTON|左箭头按钮。|
|AFX_HTRIGHTBUTTON|向右箭头按钮。|
|AFX_HTMENU|向下箭头菜单按钮。|
|HTNOWHERE|默认值;不表示命令。|

### <a name="remarks"></a>备注

默认情况下，标题按钮不与命令相关联。

标题按钮在右对齐或左对齐。

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a> CMFCCaptionButton::GetHit

返回由按钮表示的命令。

```
UINT GetHit() const;
```

### <a name="return-value"></a>返回值

按钮所表示的命令。

下表列出了可能的返回值。

|值|命令|
|-----------|-------------|
|AFX_HTCLOSE|"关闭" 按钮。|
|HTMINBUTTON|最小化按钮。|
|HTMAXBUTTON|最大化按钮。|
|AFX_HTLEFTBUTTON|左箭头按钮。|
|AFX_HTRIGHTBUTTON|向右箭头按钮。|
|AFX_HTMENU|向下箭头菜单按钮。|
|HTNOWHERE|默认值;不表示命令。|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a> CMFCCaptionButton::GetIconID

返回与按钮关联的图像 ID。

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>parameters

*bHorz*<br/>
中对于左箭头或右箭头图像 Id 为 TRUE;对于向上或向下箭头图像 Id 为 FALSE。

*bMaximized*<br/>
中如果最大化映像 ID，则为 TRUE;如果图像 ID 最小化，则为 FALSE。

### <a name="return-value"></a>返回值

映像 ID。

### <a name="remarks"></a>备注

参数指定最小化或最大化标题按钮的图像 Id。

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a> CMFCCaptionButton::GetRect

返回由按钮占据的矩形。

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>返回值

表示按钮位置的矩形。

### <a name="remarks"></a>备注

如果看不到该按钮，则返回的大小为0。

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a> CMFCCaptionButton：： GetSize

返回按钮的宽度和高度。

```
static CSize GetSize();
```

### <a name="return-value"></a>返回值

按钮的外部尺寸。

### <a name="remarks"></a>备注

返回的大小包括按钮边距和边框。

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a> CMFCCaptionButton::IsMiniFrameButton

指示是否将标题栏高度设置为小尺寸。

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>返回值

如果标题设置为小尺寸，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a> CMFCCaptionButton：： Move

设置按钮绘制位置和窗口显示状态。

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>parameters

*ptTo*<br/>
中新位置。

*bHide*<br/>
中是否显示按钮。

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a> CMFCCaptionButton：： OnDraw

绘制标题按钮。

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向按钮的设备上下文的指针。

*bActive*<br/>
中是否绘制活动按钮图像。

*bHorz*<br/>
中保留以供在派生类中使用。

*bMaximized*<br/>
中是否绘制最大化按钮图像。

*bDisabled*<br/>
中是否绘制已启用的按钮图像。

### <a name="remarks"></a>备注

如果按钮是最大化或最小化按钮，则使用 *bMaximized* 参数。

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a> CMFCCaptionButton::SetMiniFrameButton

设置标题栏的小尺寸。

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>parameters

*bSet*<br/>
中对于微型标题栏高度为 TRUE;对于默认标题栏高度为 FALSE。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd 类](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane 类](../../mfc/reference/cdockablepane-class.md)
