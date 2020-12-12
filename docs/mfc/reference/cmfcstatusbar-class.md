---
description: 了解详细信息： CMFCStatusBar 类
title: CMFCStatusBar 类
ms.date: 11/19/2018
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
ms.openlocfilehash: 79ba7c749a73406893173d7486fd5df208a37b83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307075"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar 类

`CMFCStatusBar`类实现类似于类的状态栏 `CStatusBar` 。 但是，`CMFCStatusBar` 类具有 `CStatusBar` 类未提供的功能，例如显示图像、动画和进度栏的功能，以及对鼠标双击作出响应的功能。

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCStatusBar：： CalcFixedLayout](#calcfixedlayout)| (重写 [CBasePane：： CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout)。 ) |
|[CMFCStatusBar：： CommandToIndex](#commandtoindex)||
|[CMFCStatusBar：： Create](#create)|创建一个控件栏并将其附加到 [CPane](../../mfc/reference/cpane-class.md) 对象。  (重写 [CPane：： Create](../../mfc/reference/cpane-class.md#create). ) |
|[CMFCStatusBar：： CreateEx](#createex)|创建一个控件栏并将其附加到 [CPane](../../mfc/reference/cpane-class.md) 对象。  (重写 [CPane：： CreateEx](../../mfc/reference/cpane-class.md#createex)。 ) |
|[CMFCStatusBar：:D oesAllowDynInsertBefore](#doesallowdyninsertbefore)|确定是否可以在此窗格和父框架之间动态插入另一个窗格。  (重写 [CBasePane：:D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)。 ) |
|[CMFCStatusBar：： EnablePaneDoubleClick](#enablepanedoubleclick)|启用或禁用在状态栏上双击鼠标的操作。|
|[CMFCStatusBar：： EnablePaneProgressBar](#enablepaneprogressbar)|在指定窗格上显示进度栏。|
|[CMFCStatusBar：： GetCount](#getcount)|返回状态栏上窗格的数目。|
|[CMFCStatusBar：： GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar：： GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar：： GetItemID](#getitemid)||
|[CMFCStatusBar：： GetItemRect](#getitemrect)||
|[CMFCStatusBar：： GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar：： GetPaneProgress](#getpaneprogress)||
|[CMFCStatusBar：： GetPaneStyle](#getpanestyle)|返回窗格样式。  (重写 [CBasePane：： GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle)。 ) |
|[CMFCStatusBar：： GetPaneText](#getpanetext)||
|[CMFCStatusBar：： GetPaneWidth](#getpanewidth)|返回状态栏的指定窗格的宽度（以像素为单位）。|
|[CMFCStatusBar：： GetTipText](#gettiptext)|返回状态栏的指定窗格的工具提示文本。|
|[CMFCStatusBar：： InvalidatePaneContent](#invalidatepanecontent)|使指定的窗格失效并重新绘制其内容。|
|[CMFCStatusBar：:P reCreateWindow](#precreatewindow)|在创建附加到此对象的 Windows 窗口之前由框架调用 `CWnd` 。  (将替代 [CWnd：:P recreatewindow](../../mfc/reference/cwnd-class.md#precreatewindow)。 ) |
|[CMFCStatusBar：： SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar：： SetIndicators](#setindicators)||
|[CMFCStatusBar：： SetPaneAnimation](#setpaneanimation)|将动画分配到指定窗格。|
|[CMFCStatusBar：： SetPaneBackgroundColor](#setpanebackgroundcolor)|设置状态栏的指定窗格的背景色。|
|[CMFCStatusBar：： SetPaneIcon](#setpaneicon)|设置状态栏的指定窗格的指示器图标。|
|[CMFCStatusBar：： SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar：： SetPaneProgress](#setpaneprogress)|为状态栏的指定窗格设置进度栏的当前进度。|
|[CMFCStatusBar：： SetPaneStyle](#setpanestyle)|设置窗格的样式。  (重写 [CBasePane：： SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle)。 ) |
|[CMFCStatusBar：： SetPaneText](#setpanetext)||
|[CMFCStatusBar：： SetPaneTextColor](#setpanetextcolor)|设置状态栏的指定窗格的文本颜色。|
|[CMFCStatusBar：： SetPaneWidth](#setpanewidth)|设置状态栏的指定窗格的宽度（以像素为单位）。|
|[CMFCStatusBar：： SetTipText](#settiptext)|设置状态栏的指定窗格的工具提示文本。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCStatusBar：： OnDrawPane](#ondrawpane)|在重绘状态栏的窗格时由框架调用。|

## <a name="remarks"></a>备注

下图显示了状态栏 [演示示例](../../overview/visual-cpp-samples.md) 应用程序中状态栏的图表。

![CMFCStatusBar 示例](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar 示例")

## <a name="examples"></a>示例

下面的示例演示应用程序用于调用类中的各种方法的局部变量 `CMFCStatusBar` 。 这些变量在 StatusBarDemoView 中声明。 主框架在 Mainfrm.cpp 中声明，文档在 StatusBarDemoDoc 中声明，并在 StatusBarDemoView 中声明。 此代码片段是 [状态栏演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

下面的示例演示如何 `CMFCStatusBar` 通过在 `GetStatusBar` mainfrm.cpp 中引入方法，然后从 StatusBarDemoView 中的方法调用此方法来获取对对象的引用 `GetStatusBar` 。 此代码片段是 [状态栏演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

下面的示例演示如何在 StatusBarDemoView 中调用类中的各种方法 `CMFCStatusBar` 。 常量在 Mainfrm.cpp 中声明。 该示例演示如何设置图标，设置状态栏窗格的工具提示文本，在指定的窗格上显示进度栏，为指定的窗格分配动画，设置状态栏窗格的文本和宽度，并为状态栏窗格设置进度栏的当前进度指示器。 此代码片段是 [状态栏演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxstatusbar

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCStatusBar：： CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>parameters

中 *bStretch*<br/>
中 *bHorz*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a> CMFCStatusBar：： CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>parameters

中 *nIDFind*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarcreate"></a><a name="create"></a> CMFCStatusBar：： Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>parameters

中 *pParentWnd*<br/>
中 *dwStyle*<br/>
中 *nID*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a> CMFCStatusBar：： CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>parameters

中 *pParentWnd*<br/>
中 *dwCtrlStyle*<br/>
中 *dwStyle*<br/>
中 *nID*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCStatusBar：:D oesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a> CMFCStatusBar：： EnablePaneDoubleClick

启用或禁用在状态栏上双击鼠标的操作。

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中如果为 TRUE，则启用鼠标双击的处理。 否则，请双击，禁用鼠标处理。

### <a name="remarks"></a>备注

如果启用状态栏来处理双击，则每当用户双击状态栏窗格时，Windows 会将 WM_COMMAND 通知连同资源 ID 一起发送到状态栏的所有者。

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a> CMFCStatusBar：： EnablePaneProgressBar

在指定窗格上显示进度栏。

```cpp
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要启用其进度栏的窗格的索引。

*nTotal*<br/>
中指定进度栏的最大值。

*bDisplayText*<br/>
中指定进度栏是否应显示当前进度值。

*clrBar*<br/>
中指定进度栏的背景色。

*clrBarDest*<br/>
中指定进度栏背景的辅助颜色。 使用与 *clrBar* 不同的值，以通过混合到渐变的颜色进行填充。

*clrProgressText*<br/>
中指定进度栏文本的颜色。

### <a name="remarks"></a>备注

如果要禁用进度栏调用 `EnablePaneProgressBar` ，请将 *nTotal* 设置为-1。 默认情况下， *nTotal* 设置为100。 因此，您不需要进行任何其他计算来以百分比形式显示进度。

应为 *clrBar* 和 *clrBarDest* 传递不同的值，以便进度栏的背景色显示混合为渐变的颜色。 .

若要设置当前进度，请调用 [CMFCStatusBar：： SetPaneProgress](#setpaneprogress) 方法。

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a> CMFCStatusBar：： GetCount

检索状态栏中窗格的数目。

```
int GetCount() const;
```

### <a name="return-value"></a>返回值

状态栏中窗格的数目。

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a> CMFCStatusBar：： GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCStatusBar：： GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>parameters

中 *rect*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a> CMFCStatusBar：： GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a> CMFCStatusBar：： GetItemRect

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>
中 *lpRect*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a> CMFCStatusBar：： GetPaneInfo

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>
中 *nID*<br/>
中 *nStyle*<br/>
中 *cxWidth*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a> CMFCStatusBar：： GetPaneProgress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a> CMFCStatusBar：： GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a> CMFCStatusBar：： GetPaneText

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>
中 *s*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a> CMFCStatusBar：： GetPaneWidth

检索状态栏的窗格宽度。

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定状态栏窗格的索引。

### <a name="return-value"></a>返回值

*NIndex* 指定的状态栏窗格的宽度;否则，如果不存在状态栏窗格，则为零。

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a> CMFCStatusBar：： GetTipText

检索状态栏的窗格的工具提示文本。

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要为其检索工具提示文本的窗格的索引。

### <a name="return-value"></a>返回值

*NIndex* 指定的状态栏窗格的工具提示文本。 否则，如果指定的 *nIndex* 不存在状态栏窗格，则为空字符串; 如果其工具提示文本为空，则为。

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a> CMFCStatusBar：： InvalidatePaneContent

使状态栏窗格无效并重新绘制其内容。

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要使其内容无效并重新绘制的窗格的索引。

### <a name="remarks"></a>备注

如果状态栏处于无效状态，则会将其标记为要重绘。 当 `UpdateWindow` 方法向方法发送 WM_PAINT 消息时，Windows 将重绘该消息 `OnPaint` 。

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a> CMFCStatusBar：： OnDrawPane

重新绘制状态栏的窗格。

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中一个指针，指向用于绘制的设备上下文。

*pPane*<br/>
中指向 `CMFCStatusBarPaneInfo` 结构的指针，该结构包含要重新绘制的窗格的相关信息。

### <a name="remarks"></a>备注

默认情况下， `OnDrawPane` 根据窗格的样式和内容，使用设备上下文 *pDC* 重绘窗格。

在派生类中重写此方法 `CMFCStatusBar` 以自定义窗格的外观。

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a> CMFCStatusBar：:P reCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>parameters

中 *cs*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a> CMFCStatusBar：： SetDrawExtendedArea

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>parameters

中 *bSet*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a> CMFCStatusBar：： SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>parameters

中 *lpIDArray*<br/>
中 *nIDCount*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a> CMFCStatusBar：： SetPaneAnimation

将动画分配到指定窗格。

```cpp
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要向其分配动画的窗格的索引。

*hImageList*<br/>
中指定包含动画帧的图像列表的句柄。

*nFrameRate*<br/>
中指定动画的帧速率（以毫秒为单位）。

*bUpdate*<br/>
中如果为 TRUE，则立即更新窗格内容。 否则，窗格内容会在其失效时进行更新。

### <a name="remarks"></a>备注

如果要禁用当前动画，请调用， `SetPaneAnimation` 并 `hImageList` 将设置为 NULL。

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a> CMFCStatusBar：： SetPaneBackgroundColor

设置 "状态栏" 窗格的背景色。

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要为其设置新背景色的窗格的索引。

*clrBackground*<br/>
中指定新的背景色。

*bUpdate*<br/>
中如果为 TRUE，则立即更新窗格内容。 否则，在窗格通过其他方法失效之前，请不要更新窗格内容。

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a> CMFCStatusBar：： SetPaneIcon

设置状态栏窗格的图标。

```cpp
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要为其设置图像的窗格的索引。

*hIcon*<br/>
中指定要设置为窗格图像的图标的句柄。

*bUpdate*<br/>
中指定是否立即更新窗格内容。

*hBmp*<br/>
中指定要设置为窗格图像的位图的句柄。

*clrTransparent*<br/>
中指定 *hBmp* 表示的位图的透明颜色。

### <a name="remarks"></a>备注

可以将 HICON 或 HBITMAP 与透明色一起传递以设置窗格的图像。 如果不想再显示图像，请将 NULL 值作为图像句柄传递。

如果有任何正在运行的动画已设置 [CMFCStatusBar：： SetPaneAnimation](#setpaneanimation) ，则将停止动画。

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a> CMFCStatusBar：： SetPaneInfo

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>
中 *nID*<br/>
中 *nStyle*<br/>
中 *cxWidth*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a> CMFCStatusBar：： SetPaneProgress

为指定窗格设置进度栏的当前进度指示器。

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要为其更新进度指示器的窗格的索引。

*nCurr*<br/>
中指定进度指示器的当前值。

*bUpdate*<br/>
中指定是否应立即更新窗格。

### <a name="remarks"></a>备注

如果要更新指定窗格中进度栏的进度指示器，请调用此方法。

若要将此函数用于给定窗格，必须先调用 [CMFCStatusBar：： EnablePaneProgressBar](#enablepaneprogressbar) 。

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a> CMFCStatusBar：： SetPaneStyle

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>
中 *nStyle*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a> CMFCStatusBar：： SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>parameters

中 *nIndex*<br/>
中 *lpszNewText*<br/>
中 *bUpdate*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a> CMFCStatusBar：： SetPaneTextColor

设置指定窗格的文本颜色。

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定要为其分配新文本颜色的窗格的索引。

*clrText*<br/>
中指定文本颜色。

*bUpdate*<br/>
中如果为 TRUE，则立即更新窗格内容。 否则，在窗格通过其他方法失效之前，请不要更新窗格内容。

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a> CMFCStatusBar：： SetPaneWidth

设置状态栏窗格的宽度。

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中要为其设置新宽度的状态栏窗格的索引。

*cx*<br/>
中状态栏窗格的新宽度（以像素为单位）。

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a> CMFCStatusBar：： SetTipText

设置状态栏窗格的工具提示文本。

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中要将工具提示文本分配到的窗格的索引。

*pszTipText*<br/>
中新的工具提示文本。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPane 类](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar 类](../../mfc/reference/cstatusbar-class.md)
