---
description: 了解详细信息： CMFCVisualManagerVS2005 类
title: CMFCVisualManagerVS2005 类
ms.date: 11/04/2016
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
ms.openlocfilehash: 74192e1c0e4c7189a64d872bcc1761cf21e5365d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331642"
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFCVisualManagerVS2005 类

`CMFCVisualManagerVS2005` 为应用程序提供 2005 Microsoft Visual Studio 的外观。

## <a name="syntax"></a>语法

```
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCVisualManagerVS2005：： GetDockingTabsBordersSize](#getdockingtabsborderssize)|框架在绘制停靠和选项卡式的窗格时调用此方法。  (重写 [CMFCVisualManager：： GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize)。 ) |
|[CMFCVisualManagerVS2005：： GetMDITabsBordersSize](#getmditabsborderssize)|框架在绘制窗口之前调用此方法来确定 MDITabs 窗口的边框大小。  (重写 [CMFCVisualManager：： GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)。 ) |
|[CMFCVisualManagerVS2005：： GetPropertyGridGroupColor](#getpropertygridgroupcolor)| (重写 [CMFCVisualManagerOffice2003：： GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor)。 ) |
|[CMFCVisualManagerVS2005：： GetTabFrameColors](#gettabframecolors)| (重写 [CMFCVisualManagerOffice2003：： GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors)。 ) |
|[CMFCVisualManagerVS2005：： HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|返回自动隐藏按钮是否在当前可视化管理器中重叠。  (重写 [CMFCVisualManager：： HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons)。 ) |
|[CMFCVisualManagerVS2005：： OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)| (重写 [CMFCVisualManagerOffice2003：： OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder)。 ) |
|[CMFCVisualManagerVS2005：： OnDrawCaptionButton](#ondrawcaptionbutton)|（重写 `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`。）|
|[CMFCVisualManagerVS2005：： OnDrawPaneCaption](#ondrawpanecaption)| (重写 [CMFCVisualManagerOffice2003：： OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption)。 ) |
|[CMFCVisualManagerVS2005：： OnDrawSeparator](#ondrawseparator)| (重写 [CMFCVisualManagerOffice2003：： OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator)。 ) |
|[CMFCVisualManagerVS2005：： OnDrawTab](#ondrawtab)| (重写 [CMFCVisualManagerOffice2003：： OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab)。 ) |
|[CMFCVisualManagerVS2005：： OnDrawToolBoxFrame](#ondrawtoolboxframe)| (重写 [CMFCVisualManager：： OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe)。 ) |
|[CMFCVisualManagerVS2005：： OnEraseTabsArea](#onerasetabsarea)| (重写 [CMFCVisualManagerOffice2003：： OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea)。 ) |
|[CMFCVisualManagerVS2005：： OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)| (重写 [CMFCVisualManagerOffice2003：： OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground)。 ) |
|[CMFCVisualManagerVS2005：： OnFillHighlightedArea](#onfillhighlightedarea)| (重写 [CMFCVisualManagerOffice2003：： OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea)。 ) |
|[CMFCVisualManagerVS2005：： OnFillMiniFrameCaption](#onfillminiframecaption)|（重写 `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`。）|
|[CMFCVisualManagerVS2005：： OnUpdateSystemColors](#onupdatesystemcolors)| (重写 [CMFCVisualManagerOffice2003：： OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors)。 ) |

## <a name="remarks"></a>备注

使用 CMFCVisualManagerVS2005 类可以更改应用程序的可视外观，使其与 Microsoft Visual Studio 2005 的外观类似。

此类的所有成员都是派生自此类（ [CMFCVisualManager 类](../../mfc/reference/cmfcvisualmanager-class.md)）的祖先的虚函数。

## <a name="example"></a>示例

下面的示例演示如何使用视觉对象管理器和2005。 此代码片段是 [桌面警报演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)

[CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)

## <a name="requirements"></a>要求

**标头：** afxvisualmanagervs2005

## <a name="cmfcvisualmanagervs2005getdockingtabsborderssize"></a><a name="getdockingtabsborderssize"></a> CMFCVisualManagerVS2005：： GetDockingTabsBordersSize

```
virtual int GetDockingTabsBordersSize();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005getmditabsborderssize"></a><a name="getmditabsborderssize"></a> CMFCVisualManagerVS2005：： GetMDITabsBordersSize

```
virtual int GetMDITabsBordersSize();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005getpropertygridgroupcolor"></a><a name="getpropertygridgroupcolor"></a> CMFCVisualManagerVS2005：： GetPropertyGridGroupColor

```
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```

### <a name="parameters"></a>parameters

中 *pPropList*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005gettabframecolors"></a><a name="gettabframecolors"></a> CMFCVisualManagerVS2005：： GetTabFrameColors

```
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,
    COLORREF& clrDark,
    COLORREF& clrBlack,
    COLORREF& clrHighlight,
    COLORREF& clrFace,
    COLORREF& clrDarkShadow,
    COLORREF& clrLight,
    CBrush*& pbrFace,
    CBrush*& pbrBlack);
```

### <a name="parameters"></a>parameters

中 *pTabWnd*<br/>
中 *clrDark*<br/>
中 *clrBlack*<br/>
中 *clrHighlight*<br/>
中 *clrFace*<br/>
中 *clrDarkShadow*<br/>
中 *clrLight*<br/>
中 *pbrFace*<br/>
中 *pbrBlack*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005hasoverlappedautohidebuttons"></a><a name="hasoverlappedautohidebuttons"></a> CMFCVisualManagerVS2005：： HasOverlappedAutoHideButtons

```
virtual BOOL HasOverlappedAutoHideButtons() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005ondrawautohidebuttonborder"></a><a name="ondrawautohidebuttonborder"></a> CMFCVisualManagerVS2005：： OnDrawAutoHideButtonBorder

```
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rectBounds*<br/>
中 *rectBorderSize*<br/>
中 *pButton*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005ondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a> CMFCVisualManagerVS2005：： OnDrawCaptionButton

```
virtual void OnDrawCaptionButton(
    CDC* pDC,
    CMFCCaptionButton* pButton,
    BOOL bActive,
    BOOL bHorz,
    BOOL bMaximized,
    BOOL bDisabled,
    int nImageID = -1);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *pButton*<br/>
中 *bActive*<br/>
中 *bHorz*<br/>
中 *bMaximized*<br/>
中 *bDisabled*<br/>
中 *nImageID*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005ondrawpanecaption"></a><a name="ondrawpanecaption"></a> CMFCVisualManagerVS2005：： OnDrawPaneCaption

```
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,
    CDockablePane* pBar,
    BOOL bActive,
    CRect rectCaption,
    CRect rectButtons);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *pBar*<br/>
中 *bActive*<br/>
中 *rectCaption*<br/>
中 *rectButtons*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005ondrawseparator"></a><a name="ondrawseparator"></a> CMFCVisualManagerVS2005：： OnDrawSeparator

```
virtual void OnDrawSeparator(
    CDC* pDC,
    CBasePane* pBar,
    CRect rect,
    BOOL bIsHoriz);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *pBar*<br/>
中 *rect*<br/>
中 *bIsHoriz*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005ondrawtab"></a><a name="ondrawtab"></a> CMFCVisualManagerVS2005：： OnDrawTab

```
virtual void OnDrawTab(
    CDC* pDC,
    CRect rectTab,
    int iTab,
    BOOL bIsActive,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rectTab*<br/>
中 *iTab*<br/>
中 *bIsActive*<br/>
中 *pTabWnd*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005ondrawtoolboxframe"></a><a name="ondrawtoolboxframe"></a> CMFCVisualManagerVS2005：： OnDrawToolBoxFrame

```
virtual void OnDrawToolBoxFrame(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rect*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005onerasetabsarea"></a><a name="onerasetabsarea"></a> CMFCVisualManagerVS2005：： OnEraseTabsArea

```
virtual void OnEraseTabsArea(
    CDC* pDC,
    CRect rect,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rect*<br/>
中 *pTabWnd*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005onfillautohidebuttonbackground"></a><a name="onfillautohidebuttonbackground"></a> CMFCVisualManagerVS2005：： OnFillAutoHideButtonBackground

```
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,
    CRect rect,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rect*<br/>
中 *pButton*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005onfillhighlightedarea"></a><a name="onfillhighlightedarea"></a> CMFCVisualManagerVS2005：： OnFillHighlightedArea

```
virtual void OnFillHighlightedArea(
    CDC* pDC,
    CRect rect,
    CBrush* pBrush,
    CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rect*<br/>
中 *pBrush*<br/>
中 *pButton*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005onfillminiframecaption"></a><a name="onfillminiframecaption"></a> CMFCVisualManagerVS2005：： OnFillMiniFrameCaption

```
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,
    CRect rectCaption,
    CPaneFrameWnd* pFrameWnd,
    BOOL bActive);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>
中 *rectCaption*<br/>
中 *pFrameWnd*<br/>
中 *bActive*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcvisualmanagervs2005onupdatesystemcolors"></a><a name="onupdatesystemcolors"></a> CMFCVisualManagerVS2005：： OnUpdateSystemColors

```
virtual void OnUpdateSystemColors();
```

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager 类](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerOfficeXP 类](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)<br/>
[CMFCVisualManagerWindows 类](../../mfc/reference/cmfcvisualmanagerwindows-class.md)<br/>
[CMFCVisualManagerOffice2003 类](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)
