---
description: 了解详细信息： CMFCRibbonColorButton 类
title: CMFCRibbonColorButton 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: a350339559febdc9346dcf8b342d274d00bab391
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293711"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton 类

`CMFCRibbonColorButton` 类用于实现可添加到功能区栏的颜色按钮。 功能区颜色按钮显示包含一个或多个调色板的下拉菜单。

## <a name="syntax"></a>语法

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonColorButton：： AddColorsGroup](#addcolorsgroup)|将一组颜色添加到常规颜色区域。|
|[CMFCRibbonColorButton：： EnableAutomaticButton](#enableautomaticbutton)|指定是否启用  “自动”按钮。|
|[CMFCRibbonColorButton：： EnableOtherButton](#enableotherbutton)|启用“其他”  按钮。|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton：： GetColor](#getcolor)|返回当前选定的颜色。|
|[CMFCRibbonColorButton：： GetColorBoxSize](#getcolorboxsize)|返回在颜色栏上显示的颜色元素的大小。|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton：： GetHighlightedColor](#gethighlightedcolor)|返回调色板弹出窗口上当前选定的元素的颜色。|
|[CMFCRibbonColorButton：： RemoveAllColorGroups](#removeallcolorgroups)|删除常规颜色区域中所有颜色组。|
|[CMFCRibbonColorButton：： SetColor](#setcolor)|选择常规颜色区域中的某种颜色。|
|[CMFCRibbonColorButton：： SetColorBoxSize](#setcolorboxsize)|设置在颜色条上显示的所有颜色元素的大小。|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton：： SetDocumentColors](#setdocumentcolors)|指定要在文档颜色区域中显示的 RGB 值列表。|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>备注

功能区颜色按钮显示用户按下它时的颜色条。 默认情况下，此颜色条包含称为常规颜色区域的颜色选择调色板。 （可选）颜色条包含一个  “自动”按钮，该按钮允许用户选择默认颜色，以及包含一个“其他”  按钮，该按钮用于显示包含其他颜色的调色板弹出窗口。

## <a name="example"></a>示例

下面的示例演示了如何使用 `CMFCRibbonColorButton` 类中的各种方法。 该示例演示了如何构造 `CMFCRibbonColorButton` 对象、设置大图像、启用  “自动”按钮、启用  “其他”按钮、设置列数、设置颜色条上显示的所有颜色元素的大小、将一组颜色添加到常规彩色区域中以及指定要在文档颜色区域中显示的 RGB 值列表。 此代码片段属于 [Draw Client 示例](../../overview/visual-cpp-samples.md)。

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>要求

**标头:** afxribboncolorbutton.h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a> CMFCRibbonColorButton：： AddColorsGroup

将一组颜色添加到常规颜色区域。

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>parameters

*lpszName*<br/>
中组名称。

*lstColors*<br/>
中颜色的列表。

*bContiguousColumns*<br/>
中控制颜色项在组中的显示方式。 如果为 TRUE，则绘制颜色项时不使用垂直间距。 如果为 FALSE，则使用垂直间距绘制颜色项。

### <a name="remarks"></a>备注

使用此函数可以使颜色弹出窗口显示多组颜色。 您可以控制颜色在组中的显示方式。

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a> CMFCRibbonColorButton：： CMFCRibbonColorButton

构造 `CMFCRibbonColorButton` 对象。

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>parameters

*nID*<br/>
中指定当用户单击按钮时要执行的命令的命令 ID。

*lpszText*<br/>
中指定要在按钮上显示的文本。

*nSmallImageIndex*<br/>
中要在按钮上显示的小图像的从零开始的索引。

*color*<br/>
中按钮的颜色 (默认为黑色) 。

*bSimpleButtonLook*<br/>
中如果为 TRUE，则将按钮绘制为一个简单的矩形。

*nLargeImageIndex*<br/>
中要在按钮上显示的大图像的从零开始的索引。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCRibbonColorButton：： EnableAutomaticButton

指定是否启用  “自动”按钮。

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中" **自动** " 按钮的标签。

*colorAutomatic*<br/>
中指定 **自动** 按钮默认颜色的 RGB 值。

*bEnable*<br/>
中如果启用 " **自动** " 按钮，则为 TRUE;如果已禁用，则为 FALSE。

*lpszToolTip*<br/>
中" **自动** " 按钮的工具提示。

*bOnTop*<br/>
中指定 **自动** 按钮是否位于调色板之前的顶部。

*bDrawBorder*<br/>
中如果应用程序在功能区颜色按钮的颜色栏周围绘制边框，则为 TRUE。 颜色条显示当前选定的颜色。 如果应用程序不绘制边框，则为 FALSE

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCRibbonColorButton：： EnableOtherButton

启用“其他”  按钮。

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
按钮的标签。

*lpszToolTip*<br/>
" **其他** " 按钮的工具提示文本。

### <a name="remarks"></a>备注

" **另** 一个" 按钮是显示在颜色组下方的按钮。 当用户单击 **另** 一个按钮时，它会显示 "颜色" 对话框。

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCRibbonColorButton：： GetAutomaticColor

检索当前自动按钮颜色。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>返回值

表示当前自动按钮颜色的 RGB 颜色值。

### <a name="remarks"></a>备注

自动按钮颜色由 `colorAutomatic` 传递给方法的参数设置 `CMFCRibbonColorButton::EnableAutomaticButton` 。

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a> CMFCRibbonColorButton：： GetColor

返回当前选定的颜色。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>返回值

通过单击按钮选择的颜色。

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a> CMFCRibbonColorButton：： GetColorBoxSize

返回在颜色栏上显示的颜色元素的大小。

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>返回值

下拉调色板中颜色按钮的大小。

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a> CMFCRibbonColorButton：： GetColumns

获取功能区颜色按钮的库显示行中的项数。

```
int GetColumns() const;
```

### <a name="return-value"></a>返回值

返回每行中的图标数。

### <a name="remarks"></a>备注

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a> CMFCRibbonColorButton：： GetHighlightedColor

返回弹出调色板上当前选定的元素的颜色。

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>返回值

弹出调色板上当前选定的元素的颜色。

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a> CMFCRibbonColorButton：： RemoveAllColorGroups

删除常规颜色区域中所有颜色组。

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a> CMFCRibbonColorButton：： SetColor

选择常规颜色区域中的某种颜色。

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>parameters

*color*<br/>
中要设置的颜色。

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a> CMFCRibbonColorButton：： SetColorBoxSize

设置在颜色条上显示的所有颜色元素的大小。

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>parameters

*sizeBox*<br/>
中调色板中的颜色按钮的新大小。

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a> CMFCRibbonColorButton：： SetColorName

为指定的颜色设置新名称。

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>parameters

*color*<br/>
中颜色的 RGB 值。

*strName*<br/>
中指定颜色的新名称。

### <a name="remarks"></a>备注

由于 `CMFCColorBar::SetColorName` 此方法调用，因此此方法会更改应用程序的所有对象中的指定颜色的名称 `CMFCColorBar` 。

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a> CMFCRibbonColorButton：： SetColumns

设置在用户颜色选择过程中向用户显示的颜色表中显示的列数。

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>parameters

*nColumns*<br/>
中每行中要显示的颜色图标数。

### <a name="remarks"></a>备注

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a> CMFCRibbonColorButton：： SetDocumentColors

指定要在文档颜色区域中显示的 RGB 值列表。

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中要与文档颜色一起显示的文本。

*lstColors*<br/>
中对 RGB 值的列表的引用。

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a> CMFCRibbonColorButton：： SetPalette

指定在颜色表中显示颜色按钮时要显示的标准颜色。

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>parameters

*pPalette*<br/>
中指向调色板的指针。

### <a name="remarks"></a>备注

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a> CMFCRibbonColorButton：： UpdateColor

当用户在用户单击颜色按钮时显示的颜色表中选择颜色时，由框架调用。

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>parameters

*color*<br/>
中用户选择的颜色。

### <a name="remarks"></a>备注

`CMFCRibbonColorButton::UpdateColor`方法使用 BN_CLICKED 标准通知发送 WM_COMMAND 消息，从而更改当前选择的按钮颜色并通知其父项。 使用 [CMFCRibbonColorButton：： GetColor](#getcolor) 方法检索选定的颜色。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery 类](../../mfc/reference/cmfcribbongallery-class.md)
