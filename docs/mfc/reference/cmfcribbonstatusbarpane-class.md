---
description: 了解详细信息： CMFCRibbonStatusBarPane 类
title: CMFCRibbonStatusBarPane 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
ms.openlocfilehash: 4ddbee5a6c44411ef2ac34bff3e07b47c3d950a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264981"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane 类

`CMFCRibbonStatusBarPane`类实现可添加到功能区状态栏的功能区元素。

## <a name="syntax"></a>语法

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonStatusBarPane：： CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|构造并初始化一个 `CMFCRibbonStatusBarPane` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonStatusBarPane：： GetAlmostLargeText](#getalmostlargetext)|返回一个字符串，该字符串定义可以在不截断的情况下显示在窗格中的最长文本字符串。|
|[CMFCRibbonStatusBarPane：： GetTextAlign](#gettextalign)|返回文本对齐方式的当前设置。|
|[CMFCRibbonStatusBarPane：： IsAnimation](#isanimation)|确定动画是否正在进行。|
|[CMFCRibbonStatusBarPane：： IsExtended](#isextended)|确定窗格是否位于功能区状态栏的扩展区域中。|
|[CMFCRibbonStatusBarPane：： OnDrawBorder](#ondrawborder)| (重写 [CMFCRibbonButton：： OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder)。 ) |
|[CMFCRibbonStatusBarPane：： OnFillBackground](#onfillbackground)| (重写 [CMFCRibbonButton：： OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground)。 ) |
|[CMFCRibbonStatusBarPane：： SetAlmostLargeText](#setalmostlargetext)|定义可在不截断的情况下显示在窗格中的最长文本字符串。|
|[CMFCRibbonStatusBarPane：： SetAnimationList](#setanimationlist)|向窗格分配可用于动画的图像列表。|
|[CMFCRibbonStatusBarPane：： SetTextAlign](#settextalign)|设置文本对齐方式。|
|[CMFCRibbonStatusBarPane：： StartAnimation](#startanimation)|启动分配给窗格的动画。|
|[CMFCRibbonStatusBarPane：： StopAnimation](#stopanimation)|停止分配给窗格的动画。 .|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCRibbonStatusBarPane：： OnFinishAnimation](#onfinishanimation)|当分配给窗格的动画停止时，由框架调用。|

## <a name="example"></a>示例

下面的示例演示如何使用 `CMFCRibbonStatusBarPane` 类中的各种方法。 该示例演示了如何构造 `CMFCRibbonStatusBarPane` 对象、设置状态栏窗格标签的文本对齐方式、定义可在状态栏窗格中显示的最长文本（无截断）、附加到 "状态栏" 窗格、可用于动画的图像列表以及启动动画。

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>要求

**标头：** afxribbonstatusbarpane

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a> CMFCRibbonStatusBarPane：： CMFCRibbonStatusBarPane

在状态栏中构造窗格对象。

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>parameters

*nCmdID*<br/>
中指定窗格的命令 ID。

*lpszText*<br/>
中指定要在窗格上显示的文本字符串。

*bIsStatic*<br/>
中如果为 TRUE，则不能通过单击 "状态" 窗格将其突出显示或选中。

*hIcon*<br/>
中指定要在窗格上显示的图标的句柄。

*lpszAlmostLargeText*<br/>
中指定窗格可显示的最长文本字符串。

*hBmpAnimationList*<br/>
中指定用于动画的图像列表的句柄。

*cxAnimation*<br/>
中指定用于动画的图像列表中图标的宽度（以像素为单位）。

*clrTrnsp*<br/>
中指定用于动画的图像列表中的图像的透明颜色。

*uiAnimationListResID*<br/>
中指定用于动画的图像列表的资源 ID。

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a> CMFCRibbonStatusBarPane：： GetAlmostLargeText

获取状态栏窗格可显示的最长文本字符串。

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>返回值

状态栏窗格可以显示的最长文本字符串。

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a> CMFCRibbonStatusBarPane：： GetTextAlign

获取状态栏窗格的标签文本对齐方式的当前设置。

```
int GetTextAlign() const;
```

### <a name="return-value"></a>返回值

可以是下列其中一项的当前文本对齐方式：

- TA_LEFT

- TA_CENTER

- TA_RIGHT。

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a> CMFCRibbonStatusBarPane：： IsAnimation

确定动画是否正在进行。

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>返回值

如果动画正在进行，则为 TRUE;否则为 FALSE。

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a> CMFCRibbonStatusBarPane：： IsExtended

确定窗格是否位于功能区状态栏的扩展区域中。

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>返回值

如果窗格位于状态栏的扩展区域中，则为 TRUE。 否则为 FALSE。

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a> CMFCRibbonStatusBarPane：： OnDrawBorder

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>parameters

中 *CDC&#42;*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a> CMFCRibbonStatusBarPane：： OnFillBackground

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a> CMFCRibbonStatusBarPane：： OnFinishAnimation

当分配给窗格的动画结束时，框架会调用此方法。

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>备注

`StopAnimation` 方法调用 `OnFinishAnimation` 方法，该方法可用于在动画结束时清除数据。

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a> CMFCRibbonStatusBarPane：： SetAlmostLargeText

定义可在不截断的情况下显示在状态栏窗格中的最长文本。

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>parameters

*lpszAlmostLargeText*<br/>
中指定可在不截断的情况下显示在状态栏窗格上的最长字符串。

### <a name="remarks"></a>备注

库计算 *lpszAlmostLargeText* 指定的文本大小，并相应地调整窗格的大小。 如果文本仍不能容纳在窗格中，则文本将被截断。

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a> CMFCRibbonStatusBarPane：： SetAnimationList

附加到 "状态栏" 窗格可用于动画的图像列表。

```cpp
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>parameters

*hBmpAnimationList*<br/>
中指定图像列表的句柄。

*cxAnimation*<br/>
中指定图像列表中框架的宽度（以像素为单位）。

*clrTransp*<br/>
中指定图像列表的透明色。

*uiAnimationListResID*<br/>
中指定图像列表的资源 ID。

### <a name="return-value"></a>返回值

如果图像列表成功附加到状态栏窗格，则为 TRUE;否则为 FALSE。

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a> CMFCRibbonStatusBarPane：： SetTextAlign

设置状态栏窗格标签的文本对齐方式。

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>parameters

*nAlign*<br/>
中指定文本对齐方式。

### <a name="remarks"></a>备注

*nAlign* 可以具有以下值之一：

- TA_LEFT：左对齐

- TA_CENTER：中心对齐

- TA_RIGHT：右对齐

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a> CMFCRibbonStatusBarPane：： StartAnimation

启动您分配给窗格的动画。

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>parameters

*nFrameDelay*<br/>
中指定动画帧速率（以毫秒为单位）。

*nDuration*<br/>
中指定播放动画的时间长度（以毫秒为单位）。 使用-1 表示无限循环。

### <a name="remarks"></a>备注

在使用调用之前，必须指定图像列表的句柄 `StartAnimation` `SetAnimationList` 。

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a> CMFCRibbonStatusBarPane：： StopAnimation

停止分配给状态栏窗格的动画。

```cpp
void StopAnimation();
```

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton 类](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar 类](../../mfc/reference/cmfcribbonstatusbar-class.md)
