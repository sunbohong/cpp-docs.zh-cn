---
description: 了解详细信息： CGlobalUtils 类
title: CGlobalUtils 类
ms.date: 10/18/2018
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
ms.openlocfilehash: d1e2f096825d34a907afbcdb022c550b94476906
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184096"
---
# <a name="cglobalutils-class"></a>CGlobalUtils 类

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CGlobalUtils
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CGlobalUtils::AdjustRectToWorkArea](#adjustrecttoworkarea)||
|[CGlobalUtils::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CGlobalUtils::CanBeAttached](#canbeattached)||
|[CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd](#canpanebeinfloatingmultipaneframewnd)||
|[CGlobalUtils::CheckAlignment](#checkalignment)||
|[CGlobalUtils::CyFromString](#cyfromstring)||
|[CGlobalUtils::DecimalFromString](#decimalfromstring)||
|[CGlobalUtils::FlipRect](#fliprect)||
|[CGlobalUtils::ForceAdjustLayout](#forceadjustlayout)||
|[CGlobalUtils::GetDockingManager](#getdockingmanager)||
|[CGlobalUtils::GetOppositeAlignment](#getoppositealignment)||
|[CGlobalUtils::GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||
|[CGlobalUtils::GetWndIcon](#getwndicon)||
|[CGlobalUtils::SetNewParent](#setnewparent)||
|[CGlobalUtils::StringFromCy](#stringfromcy)||
|[CGlobalUtils::StringFromDecimal](#stringfromdecimal)||

## <a name="remarks"></a>备注

## <a name="inheritance-hierarchy"></a>继承层次结构

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>要求

**标头：** afxglobalutils

## <a name="cglobalutilsadjustrecttoworkarea"></a><a name="adjustrecttoworkarea"></a> CGlobalUtils::AdjustRectToWorkArea

```cpp
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>parameters

[in，out] *rect*<br/>
中 *pRectDelta*<br/>

### <a name="remarks"></a>备注

## <a name="cglobalutilscalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a> CGlobalUtils::CalcExpectedDockedRect

```cpp
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>parameters

中 *barContainerManager*<br/>

中 *pWndTodock*<br/>

中 *ptMouse*<br/>

弄 *rectResult*<br/>

弄 *bDrawTab*<br/>

弄 *ppTargetBar*<br/>

### <a name="remarks"></a>备注

## <a name="cglobalutilscanbeattached"></a><a name="canbeattached"></a> CGlobalUtils::CanBeAttached

```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>parameters

中 *pWnd*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilscanpanebeinfloatingmultipaneframewnd"></a><a name="canpanebeinfloatingmultipaneframewnd"></a> CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd

```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>parameters

中 *pWnd*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilscheckalignment"></a><a name="checkalignment"></a> CGlobalUtils::CheckAlignment

```
BOOL CheckAlignment(
    CPoint point,
    CBasePane* pBar,
    int nSensitivity,
    const CDockingManager* pDockManager,
    BOOL bOuterEdge,
    DWORD& dwAlignment,
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,
    LPCRECT lpRectBounds = NULL) const;
```

### <a name="parameters"></a>parameters

中 *点*<br/>

中 *pBar*<br/>

中 *nSensitivity*<br/>

中 *pDockManager*<br/>

中 *bOuterEdge*<br/>

弄 *dwAlignment*<br/>

中 *dwEnabledDockBars*<br/>

中 *lpRectBounds*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilscyfromstring"></a><a name="cyfromstring"></a> CGlobalUtils::CyFromString

```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>parameters

弄 *cy*<br/>

中 *psz*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilsdecimalfromstring"></a><a name="decimalfromstring"></a> CGlobalUtils：:D ecimalFromString

```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>parameters

弄 *decimal*<br/>

中 *psz*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilsfliprect"></a><a name="fliprect"></a> CGlobalUtils::FlipRect

```cpp
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>parameters

[in，out] *rect*<br/>
中 *nDegrees*<br/>

### <a name="remarks"></a>备注

## <a name="cglobalutilsforceadjustlayout"></a><a name="forceadjustlayout"></a> CGlobalUtils::ForceAdjustLayout

```cpp
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>parameters

[in，out] *pDockManager*<br/>

中 *bForce*<br/>

中 *bForceInvisible*<br/>

### <a name="remarks"></a>备注

## <a name="cglobalutilsgetdockingmanager"></a><a name="getdockingmanager"></a> CGlobalUtils::GetDockingManager

```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>parameters

中 *pWnd*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilsgetoppositealignment"></a><a name="getoppositealignment"></a> CGlobalUtils::GetOppositeAlignment

```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>parameters

中 *dwAlign*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilsgetpaneandalignfrompoint"></a><a name="getpaneandalignfrompoint"></a> CGlobalUtils::GetPaneAndAlignFromPoint

```
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,
    CPoint pt,
    CDockablePane** ppTargetControlBar,
    DWORD& dwAlignment,
    BOOL& bTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>parameters

中 *barContainerManager*<br/>

中 *pt*<br/>

弄 *ppTargetControlBar*<br/>

弄 *dwAlignment*<br/>

弄 *bTabArea*<br/>

弄 *bCaption*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilsgetwndicon"></a><a name="getwndicon"></a> CGlobalUtils::GetWndIcon

```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>parameters

中 *pWnd*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilssetnewparent"></a><a name="setnewparent"></a> CGlobalUtils::SetNewParent

```cpp
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>parameters

中 *lstControlBars*<br/>

中 *pNewParent*<br/>

中 *bCheckVisibility*<br/>

### <a name="remarks"></a>备注

## <a name="cglobalutilsstringfromcy"></a><a name="stringfromcy"></a> CGlobalUtils::StringFromCy

```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>parameters

弄 *str*<br/>

中 *cy*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cglobalutilsstringfromdecimal"></a><a name="stringfromdecimal"></a> CGlobalUtils::StringFromDecimal

```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>parameters

弄 *str*<br/>

中 *decimal*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)
