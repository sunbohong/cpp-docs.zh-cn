---
description: 了解详细信息： CMFCCaptionBar 类
title: CMFCCaptionBar 类
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: a5dd5f968c52268935b6176115e8723a9d82e8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327744"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar 类

`CMFCCaptionBar`对象是可以显示三个元素的控件栏：按钮、文本标签和位图。 它一次只能显示一种类型的一个元素。 你可以将每个元素与控件进行左对齐、右对齐或居中对齐。 你还可将平面或 3D 样式应用于标题栏的顶部和底部边界。

## <a name="syntax"></a>语法

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCCaptionBar：： Create](#create)|创建标题栏控件，并将其附加到 `CMFCCaptionBar` 对象。|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|指示是否可以在标题栏及其父框架之间动态插入另一个窗格。  (重写 [CBasePane：:D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)。 ) |
|[CMFCCaptionBar：： EnableButton](#enablebutton)|启用或禁用标题栏上的按钮。|
|[CMFCCaptionBar：： GetAlignment](#getalignment)|返回指定元素的对齐方式。|
|[CMFCCaptionBar：： GetBorderSize](#getbordersize)|返回标题栏的边框大小。|
|[CMFCCaptionBar：： GetButtonRect](#getbuttonrect)|检索标题栏上按钮的边框。|
|[CMFCCaptionBar：： GetMargin](#getmargin)|返回标题栏元素边缘与标题栏控件边缘之间的距离。|
|[CMFCCaptionBar：： IsMessageBarMode](#ismessagebarmode)|指定标题栏是否处于消息栏模式。|
|[CMFCCaptionBar：： RemoveBitmap](#removebitmap)|从标题栏中删除位图图像。|
|[CMFCCaptionBar：： RemoveButton](#removebutton)|删除标题栏中的按钮。|
|[CMFCCaptionBar：： RemoveIcon](#removeicon)|删除标题栏中的图标。|
|[CMFCCaptionBar：： RemoveText](#removetext)|从标题栏中删除文本标签。|
|[CMFCCaptionBar：： SetBitmap](#setbitmap)|设置标题栏的位图图像。|
|[CMFCCaptionBar：： SetBorderSize](#setbordersize)|设置标题栏的边框大小。|
|[CMFCCaptionBar：： SetButton](#setbutton)|设置标题栏的按钮。|
|[CMFCCaptionBar：： SetButtonPressed](#setbuttonpressed)|指定按钮是否保持按下状态。|
|[CMFCCaptionBar：： SetButtonToolTip](#setbuttontooltip)|设置按钮的工具提示。|
|[CMFCCaptionBar：： SetFlatBorder](#setflatborder)|设置标题栏的边框样式。|
|[CMFCCaptionBar：： SetIcon](#seticon)|设置标题栏的图标。|
|[CMFCCaptionBar：： SetImageToolTip](#setimagetooltip)|为标题栏的图像设置工具提示。|
|[CMFCCaptionBar：： SetMargin](#setmargin)|设置标题栏元素边缘与标题栏控件边缘之间的距离。|
|[CMFCCaptionBar：： SetText](#settext)|设置标题栏的文本标签。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCCaptionBar：： OnDrawBackground](#ondrawbackground)|由框架调用以填充标题栏的背景。|
|[CMFCCaptionBar：： OnDrawBorder](#ondrawborder)|由框架调用，用于绘制标题栏的边框。|
|[CMFCCaptionBar：： OnDrawButton](#ondrawbutton)|由框架调用，用于绘制标题栏按钮。|
|[CMFCCaptionBar：： OnDrawImage](#ondrawimage)|由框架调用，用于绘制标题栏图像。|
|[CMFCCaptionBar：： OnDrawText](#ondrawtext)|由框架调用，用于绘制标题栏文本。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCCaptionBar：： m_clrBarBackground](#m_clrbarbackground)|标题栏的背景色。|
|[CMFCCaptionBar：： m_clrBarBorder](#m_clrbarborder)|标题栏边框的颜色。|
|[CMFCCaptionBar：： m_clrBarText](#m_clrbartext)|标题栏文本的颜色。|

## <a name="remarks"></a>备注

若要创建标题栏，请按以下步骤操作：

1. 构造 `CMFCCaptionBar` 对象。 通常，将标题栏添加到框架窗口类。

1. 调用 [CMFCCaptionBar：： create](#create) 方法创建标题栏控件，并将其附加到 `CMFCCaptionBar` 对象。

1. 调用 [CMFCCaptionBar：： SetButton](#setbutton)、 [CMFCCaptionBar：： SetText](#settext)、 [CMFCCaptionBar：： SetIcon](#seticon)和 [CMFCCaptionBar：： SetBitmap](#setbitmap) 来设置标题栏元素。

设置 button 元素时，必须为该按钮指定命令 ID。 当用户单击按钮时，标题栏会将具有此 ID 的 WM_COMMAND 消息路由到父框架窗口中。

标题栏也可以在消息栏模式下工作，该模式模拟 Microsoft Office 2007 应用程序中显示的消息栏。 在消息栏模式下，标题栏会显示一个位图、一条消息和一个按钮 (通常会打开一个对话框。 ) 可以将工具提示分配给位图。

若要启用消息栏模式，请调用 [CMFCCaptionBar：： Create](#create) 并将第四个参数 (bIsMessageBarMode) 设置为 TRUE。

## <a name="example"></a>示例

下面的示例演示了如何使用 `CMFCCaptionBar` 类中的各种方法。 该示例演示如何创建标题栏控件、设置标题栏的三维边框、设置标题栏元素边缘与标题栏控件边缘之间的距离（以像素为单位）、设置标题栏的按钮、设置按钮的工具提示、设置标题栏的文本标签、设置标题栏的位图图像，并为标题栏中的图像设置工具提示。 此代码片段是 [MS Office 2007 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxcaptionbar

## <a name="cmfccaptionbarcreate"></a><a name="create"></a> CMFCCaptionBar：： Create

创建标题栏控件，并将其附加到 `CMFCCaptionBar` 对象。

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>parameters

*dwStyle*<br/>
标题栏样式的逻辑或组合。

*pParentWnd*<br/>
标题栏控件的父窗口。

*标识号*<br/>
标题栏控件的 ID。

*nHeight*<br/>
标题栏控件的高度（以像素为单位）。 如果为-1，则根据图标的高度、文本和标题栏控件显示的按钮来计算高度。

*bIsMessageBarMode*<br/>
如果标题栏处于消息栏模式，则为 TRUE;否则为 FALSE。

### <a name="return-value"></a>返回值

如果成功创建了标题栏控件，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

可以通过 `CMFCCaptionBar` 两个步骤构造对象。 首先调用构造函数，然后调用 `Create` 方法，该方法创建 Windows 控件并将其附加到 `CMFCCaptionBar` 对象。

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCCaptionBar：:D oesAllowDynInsertBefore

指示是否可以在标题栏及其父框架之间动态插入另一个窗格。

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>返回值

除非重写，否则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a> CMFCCaptionBar：： EnableButton

启用或禁用标题栏上的按钮。

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中若要启用此按钮，则为 TRUE，否则禁用该按钮。

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a> CMFCCaptionBar：： GetAlignment

返回指定元素的对齐方式。

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>parameters

*elem*<br/>
中要为其检索对齐方式的标题栏元素。

### <a name="return-value"></a>返回值

元素的对齐方式，如按钮、位图、文本或图标。

### <a name="remarks"></a>备注

元素的对齐方式可以是下列值之一：

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a> CMFCCaptionBar：： GetBorderSize

返回标题栏的边框大小。

```
int GetBorderSize() const;
```

### <a name="return-value"></a>返回值

边框的大小（以像素为单位）。

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a> CMFCCaptionBar：： GetButtonRect

检索标题栏上按钮的边框。

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>返回值

一个 `CRect` 对象，该对象包含标题栏上按钮的边框的坐标。

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a> CMFCCaptionBar：： GetMargin

返回标题栏元素边缘与标题栏控件边缘之间的距离。

```
int GetMargin() const;
```

### <a name="return-value"></a>返回值

标题栏元素边缘与标题栏控件边缘之间的距离（以像素为单位）。

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a> CMFCCaptionBar：： IsMessageBarMode

指定标题栏是否处于消息栏模式。

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>返回值

如果标题栏处于消息栏模式，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

在消息栏模式下，标题栏显示带有工具提示、消息文本和按钮的图像。

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a> CMFCCaptionBar：： m_clrBarBackground

标题栏的背景色。

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a> CMFCCaptionBar：： m_clrBarBorder

标题栏边框的颜色。

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a> CMFCCaptionBar：： m_clrBarText

标题栏文本的颜色。

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a> CMFCCaptionBar：： OnDrawBackground

由框架调用以填充标题栏的背景。

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向标题栏的设备上下文的指针。

*rect*<br/>
中要填充的边框。

### <a name="remarks"></a>备注

`OnDrawBackground`当要填充标题栏的背景时，将调用方法。 默认实现使用 [CMFCCaptionBar：： m_clrBarBackground](#m_clrbarbackground) 颜色填充背景。

在派生类中重写此方法 `CMFCCaptionBar` 以自定义标题栏的外观。

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a> CMFCCaptionBar：： OnDrawBorder

由框架调用，用于绘制标题栏的边框。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中用于显示边框的设备上下文。

*rect*<br/>
中边框。

### <a name="remarks"></a>备注

默认情况下，边框具有平面样式。

在派生类中重写此方法 `CMFCCaptionBar` ，以自定义标题栏边框的外观。

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a> CMFCCaptionBar：： OnDrawButton

由框架调用，用于绘制标题栏按钮。

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向用于显示按钮的设备上下文的指针。

*rect*<br/>
中按钮的边框。

*strButton*<br/>
中按钮的文本标签。

*bEnabled*<br/>
中如果启用此按钮，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

在派生类中重写此方法 `CMFCCaptionBar` ，以自定义标题栏按钮的外观。

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a> CMFCCaptionBar：： OnDrawImage

由框架调用，用于绘制标题栏图像。

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向用于显示图像的设备上下文的指针。

*rect*<br/>
中指定图像的边框。

### <a name="remarks"></a>备注

在派生类中重写此方法 `CMFCCaptionBar` 以自定义图像外观。

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a> CMFCCaptionBar：： OnDrawText

由框架调用，用于绘制标题栏文本。

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向用于显示按钮的设备上下文的指针。

*rect*<br/>
中文本的边框。

*strText*<br/>
中要显示的文本字符串。

### <a name="remarks"></a>备注

默认实现使用 `CDC::DrawText` 和 [CMFCCaptionBar：： m_clrBarText](#m_clrbartext) 颜色显示文本。

在派生类中重写此方法 `CMFCCaptionBar` ，以自定义标题栏文本的外观。

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a> CMFCCaptionBar：： RemoveBitmap

从标题栏中删除位图图像。

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a> CMFCCaptionBar：： RemoveButton

删除标题栏中的按钮。

```cpp
void RemoveButton();
```

### <a name="remarks"></a>备注

标题栏元素的布局会自动调整。

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a> CMFCCaptionBar：： RemoveIcon

删除标题栏中的图标。

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a> CMFCCaptionBar：： RemoveText

从标题栏中删除文本标签。

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a> CMFCCaptionBar：： SetBitmap

设置标题栏的位图图像。

```cpp
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>parameters

*hBitmap*<br/>
中要设置的位图的句柄。

*clrTransparent*<br/>
中指定位图透明色的 RGB 值。

*bStretch*<br/>
中如果为 TRUE，则当位图不适合图像边框时，它将被拉伸。 否则，不会拉伸位图。

*bmpAlignment*<br/>
中位图的对齐方式。

### <a name="remarks"></a>备注

使用此方法可以在标题栏上设置位图。

将自动销毁上一个位图。 如果标题栏显示了一个图标，因为您调用了 [CMFCCaptionBar：： SetIcon](#seticon) 方法，则除非您通过调用 [CMFCCaptionBar：： RemoveIcon](#removeicon)删除该图标，否则将不会显示该位图。

位图按 *bmpAlignment* 参数指定的方式对齐。  此参数可能是以下 `BarElementAlignment` 值之一：

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a> CMFCCaptionBar：： SetBorderSize

设置标题栏的边框大小。

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>parameters

*nSize*<br/>
中标题栏边框的新大小（以像素为单位）。

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a> CMFCCaptionBar：： SetButton

设置标题栏的按钮。

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
按钮的命令标签。

*uiCmdUI*<br/>
按钮的命令 ID。

*btnAlignmnet*<br/>
按钮的对齐方式。

*bHasDropDownArrow*<br/>
如果按钮显示下拉箭头，则为 TRUE; 否则为 FALSE。

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a> CMFCCaptionBar：： SetButtonPressed

指定按钮是否保持按下状态。

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>parameters

*bPresed*<br/>
如果按钮保持其按下状态，则为 TRUE; 否则为 FALSE。

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a> CMFCCaptionBar：： SetButtonToolTip

设置按钮的工具提示。

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>parameters

*lpszToolTip*<br/>
中工具提示标题。

*lpszDescription*<br/>
中工具提示说明。

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a> CMFCCaptionBar：： SetFlatBorder

设置标题栏的边框样式。

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>parameters

*bFlat*<br/>
中如果标题栏的边框为平面，则为 TRUE。 如果边框为三维，则为 FALSE。

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a> CMFCCaptionBar：： SetIcon

设置标题栏的图标。

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>parameters

*hIcon*<br/>
中要设置的图标的句柄。

*iconAlignment*<br/>
中图标的对齐方式。

### <a name="remarks"></a>备注

标题栏可以显示图标或位图。 请参阅 [CMFCCaptionBar：： SetBitmap](#setbitmap) 以了解如何显示位图。 如果同时设置了图标和位图，则始终会显示图标。 调用 [CMFCCaptionBar：： RemoveIcon](#removeicon) 可从标题栏中删除图标。

图标根据 *iconAlignment* 参数对齐。 它可以是下列 `BarElementAlignment` 值之一：

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a> CMFCCaptionBar：： SetImageToolTip

为标题栏中的图像设置工具提示。

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>parameters

*lpszToolTip*<br/>
中工具提示的文本。

*lpszDescription*<br/>
中工具提示说明。

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a> CMFCCaptionBar：： SetMargin

设置标题栏元素边缘与标题栏控件边缘之间的距离。

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>parameters

*nMargin*<br/>
中标题栏元素边缘与标题栏控件边缘之间的距离（以像素为单位）。

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a> CMFCCaptionBar：： SetText

设置标题栏的文本标签。

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>parameters

*strText*<br/>
中要设置的文本字符串。

*System.windows.textalignment>*<br/>
中文本对齐方式。

### <a name="remarks"></a>备注

文本标签按 *system.windows.textalignment>* 参数指定的方式对齐。 它可以是下列 `BarElementAlignment` 值之一：

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)
