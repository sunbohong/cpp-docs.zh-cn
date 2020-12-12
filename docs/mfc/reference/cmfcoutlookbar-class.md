---
description: 了解详细信息： CMFCOutlookBar 类
title: CMFCOutlookBar 类
ms.date: 06/25/2018
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
ms.openlocfilehash: e54e44e702aaf8d6883ada6be9c127f63ecee97d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265033"
---
# <a name="cmfcoutlookbar-class"></a>CMFCOutlookBar 类

在 Microsoft Outlook 2000 或 Outlook 2003 中具有 **“导航窗格”** 可视外观的选项卡式窗格。 `CMFCOutlookBar`对象包含[CMFCOutlookBarTabCtrl 类](../../mfc/reference/cmfcoutlookbartabctrl-class.md)对象和一系列选项卡。 选项卡可以是 [CMFCOutlookBarPane 类](../../mfc/reference/cmfcoutlookbarpane-class.md) 对象或 `CWnd` 派生的对象。 对于用户，Outlook 栏显示为一系列按钮和一个显示区域。 用户单击按钮时，将显示相应控件或按钮窗格。

## <a name="syntax"></a>语法

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|默认构造函数。|
|`CMFCOutlookBar::~CMFCOutlookBar`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|指定是否可以销毁空的选项卡式窗格。  (重写 [CBaseTabbedPane：： AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane)。 ) |
|[CMFCOutlookBar：： CanAcceptPane](#canacceptpane)|确定是否可将另一个窗格停靠到 Outlook 栏窗格。  (重写 CDockablePane：： CanAcceptPane。 ) |
|[CMFCOutlookBar：： CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|确定选项卡式窗格的标题是否显示与活动选项卡相同的文本。 (重写 [CBaseTabbedPane：： CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname)。 ) |
|[CMFCOutlookBar：： Create](#create)|创建 Outlook 条形控件。|
|[CMFCOutlookBar：： CreateCustomPage](#createcustompage)|创建自定义 Outlook 栏选项卡。|
|`CMFCOutlookBar::CreateObject`|由框架用于创建此类类型的动态实例。|
|[CMFCOutlookBar：:D oesAllowDynInsertBefore](#doesallowdyninsertbefore)|确定用户是否可以在 Outlook 栏的外边缘停靠控件条。|
|[CMFCOutlookBar：： FloatTab](#floattab)|浮动一个窗格，但仅当该窗格当前驻留在可分离选项卡中时。 (重写 [CBaseTabbedPane：： FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)。 ) |
|[CMFCOutlookBar：： GetButtonsFont](#getbuttonsfont)|返回 Outlook 栏按钮上文本的字体。|
|[CMFCOutlookBar：： GetTabArea](#gettabarea)|返回 Outlook 条形图上的选项卡区域的大小和位置。  (重写 [CBaseTabbedPane：： GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea)。 ) |
|`CMFCOutlookBar::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCOutlookBar：： IsMode2003](#ismode2003)|确定 Outlook 栏的行为是否模拟 Microsoft Office Outlook 2003 (参见 "备注) "。|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|使用动画设置活动选项卡后，由 [CMFCOutlookBarTabCtrl：： SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 调用。|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|在选项卡页通过使用动画设置为活动选项卡之前，由 [CMFCOutlookBarTabCtrl：： SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 调用。|
|[CMFCOutlookBar::OnScroll](#onscroll)|如果 Outlook 面板向上或向下滚动，则由框架调用。|
|[CMFCOutlookBar：： RemoveCustomPage](#removecustompage)|删除自定义 Outlook 栏选项卡。|
|[CMFCOutlookBar：： SetButtonsFont](#setbuttonsfont)|设置 Outlook 栏按钮上文本的字体。|
|[CMFCOutlookBar：： SetMode2003](#setmode2003)|指定 Outlook 栏的行为是否模仿 Outlook 2003 (参阅备注) 。|

## <a name="remarks"></a>备注

有关 Outlook 栏的示例，请参阅 [OutlookDemo 示例： MFC OutlookDemo 应用程序](../../overview/visual-cpp-samples.md)。

## <a name="implementing-the-outlook-bar"></a>实现 Outlook 栏

若要在应用程序中使用 `CMFCOutlookBar` 控件，请执行以下步骤：

1. 将 `CMFCOutlookBar` 对象嵌入主框架窗口类。

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. 在主框架中处理 WM_CREATE 消息时，请调用 [CMFCOutlookBar：： create](#create) 方法创建 Outlook 栏选项卡控件。

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. `CMFCOutlookBarTabCtrl`使用[CBaseTabbedPane：： GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow)获取指向基础的指针。

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. 为包含按钮的每个选项卡创建 [CMFCOutlookBarPane 类](../../mfc/reference/cmfcoutlookbarpane-class.md) 对象。

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. 调用 [CMFCOutlookBarTabCtrl：： AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 以添加每个新选项卡。将 *bDetachable* 参数设置为 FALSE 可使页面不可分离。 或者，使用 [CMFCOutlookBarTabCtrl：： AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) 添加可分离的页面。

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. 若要添加 `CWnd` 派生的控件 (例如， [CMFCShellTreeCtrl 类](../../mfc/reference/cmfcshelltreectrl-class.md)) 作为选项卡，请创建控件并调用 [CMFCOutlookBarTabCtrl：： AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) 将其添加到 Outlook 栏。

> [!NOTE]
> 应为每个 [CMFCOutlookBarPane 类](../../mfc/reference/cmfcoutlookbarpane-class.md) 对象和每个派生对象使用唯一控件 id `CWnd` 。

若要在运行时动态添加或删除新页，请使用 [CMFCOutlookBar：： CreateCustomPage](#createcustompage) 和 [CMFCOutlookBar：： RemoveCustomPage](#removecustompage)。

## <a name="outlook-2003-mode"></a>Outlook 2003 模式

在 Outlook 2003 模式下，选项卡按钮位于 Outlook 栏窗格的底部。 如果没有足够的空间来显示这些按钮，则它们将显示为工具栏底部工具栏上的图标。

使用 [CMFCOutlookBar：： SetMode2003](#setmode2003) 启用 Outlook 2003 模式。 使用 [CMFCOutlookBarTabCtrl：： SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) 设置包含显示在 Outlook 栏底部的图标的位图。 位图中的图标必须按 tab 键索引排序。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxoutlookbar

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a> CMFCOutlookBar：： AllowDestroyEmptyTabbedPane

指定是否可以销毁空的选项卡式窗格。

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>返回值

如果可以销毁空的选项卡式窗格，则为 TRUE;否则为 FALSE。 默认实现始终返回 TRUE。

### <a name="remarks"></a>备注

如果无法销毁空的选项卡式窗格，框架将改为隐藏。

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a> CMFCOutlookBar：： CanAcceptPane

确定是否可将另一个窗格停靠到 Outlook 栏窗格。

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>parameters

*pBar*<br/>
中指向停靠在此窗格上的另一个窗格的指针。

### <a name="return-value"></a>返回值

如果可以将另一个窗格停靠到 Outlook 栏窗格，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

如果 Outlook 栏处于 Outlook 2003 模式，则不支持停靠，因此返回值为 FALSE。

如果 *pBar* 参数为 NULL，此方法将返回 FALSE。

否则，此方法的行为类似于基方法 [CBasePane：： CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane)，只不过即使未启用接驳，outlook 栏仍可以启用另一个 outlook 面板。

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a> CMFCOutlookBar：： CanSetCaptionTextToTabName

确定选项卡式窗格的标题是否显示与活动选项卡相同的文本。

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>返回值

如果 Outlook 栏窗口标题自动设置为活动选项卡的文本，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

使用 [CBaseTabbedPane：： EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) 可以启用或禁用此功能。

在 Outlook 2003 模式下，此设置始终处于启用状态。

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a> CMFCOutlookBar：： Create

创建 Outlook 条形控件。

```cpp
virtual BOOL Create(
    LPCTSTR lpszCaption,
    CWnd* pParentWnd,
    const RECT& rect,
    UINT nID,
    DWORD dwStyle,
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>parameters

*lpszCaption*<br/>
中指定窗口标题。

*pParentWnd*<br/>
中指定指向父窗口的指针。 值不得为 NULL。

*rect*<br/>
中指定 outlook 条形图的大小和位置（以像素为单位）。

*nID*<br/>
中指定控件 ID。 必须与应用程序中使用的其他控件 Id 不同。

*dwStyle*<br/>
中指定所需的控件条样式。 有关可能的值，请参阅 [窗口样式](../../mfc/reference/styles-used-by-mfc.md#window-styles)。

*dwControlBarStyle*<br/>
中指定特定的库定义样式。

*pContext*<br/>
中创建上下文。

### <a name="return-value"></a>返回值

如果方法成功，则为非零值;否则为0。

### <a name="remarks"></a>备注

可以通过 `CMFCOutlookBar` 两个步骤构造对象。 首先调用构造函数，然后调用，它将 `Create` 创建 outlook bar 控件并将其附加到 `CMFCOutlookBar` 对象。

请参阅 [CBasePane：： CreateEx](../../mfc/reference/cbasepane-class.md#createex) ，以获取由 *dwControlBarStyle* 指定的可用库定义样式的列表。

### <a name="example"></a>示例

下面的示例演示如何使用类的 `Create` 方法 `CMFCOutlookBar` 。 此代码片段是 [Outlook 多视图示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a> CMFCOutlookBar：： CreateCustomPage

创建自定义 Outlook 栏选项卡。

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>parameters

*lpszPageName*<br/>
中页面标签。

*bActivatePage*<br/>
中如果为 TRUE，则在创建时页将变为活动状态。

*dwEnabledDocking*<br/>
中CBRS_ALIGN_ 标志的组合，用于在分离页面时指定启用的停靠面。

*bEnableTextLabels*<br/>
中如果为 TRUE，则为位于页面上的按钮启用文本标签。

### <a name="return-value"></a>返回值

指向新创建的页的指针; 如果创建失败，则为 NULL。

### <a name="remarks"></a>备注

使用此方法可使用户创建自定义 Outlook 条形页面。 每个应用程序最多可以创建100页。 页面控件 Id 从0xF000 开始。 如果自定义 Outlook 条形页面的总数超过100，则创建失败。

使用 [CMFCOutlookBar：： RemoveCustomPage](#removecustompage) 删除自定义页。

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCOutlookBar：:D oesAllowDynInsertBefore

指定用户是否可以在 Outlook 栏的外边缘停靠窗格。

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>返回值

默认实现返回 FALSE。

### <a name="remarks"></a>备注

`DoesAllowDynInsertBefore`当框架查找要停靠动态窗格的位置时，框架将调用方法。 如果该函数返回 FALSE，则该框架不允许停靠在窗格外边缘的任何动态窗格。

通常，会将 Outlook 栏创建为静态非浮动控件。 可以在派生类中重写此函数并返回 TRUE 以更改此行为。

> [!NOTE]
> 由于动态窗格会在停靠时检查停靠静态窗格的状态，因此应尽可能将动态窗格停靠在静态窗格之后。

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a> CMFCOutlookBar：： FloatTab

浮动窗格。

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>parameters

*pBar*<br/>
中指向要浮动的窗格的指针。

*nTabID*<br/>
中要浮动的选项卡的从零开始的索引。

*dockMethod*<br/>
中指定要用于使窗格浮动的方法。  有关详细信息，请参阅 [CBaseTabbedPane：： FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)。

*bHide*<br/>
中若要在浮动前隐藏窗格，则为 TRUE;否则为 FALSE。 与此方法的基类版本不同，此参数没有默认值。

### <a name="return-value"></a>返回值

如果窗格浮动，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

此方法类似于 [CBaseTabbedPane：： FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) ，只不过它不允许 Outlook bar 控件上的最后剩余选项卡浮动。

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a> CMFCOutlookBar：： GetButtonsFont

返回 Outlook 栏的页面按钮选项卡上的文本的字体。

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>返回值

一个指针，指向用于显示 Outlook 栏页面按钮选项卡上的文本的字体对象。

### <a name="remarks"></a>备注

使用此函数可检索用于显示 Outlook 页面按钮选项卡上的文本的字体。 可以通过在 [CMFCOutlookBar：： SetButtonsFont](#setbuttonsfont)上调用来设置字体。

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a> CMFCOutlookBar：： GetTabArea

确定选项卡区域在 Outlook 栏上的大小和位置。

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>parameters

*rectTabAreaTop*<br/>
弄当函数返回时，包含 (在顶部选项卡区域的工作区坐标) 中的大小和位置。

*rectTabAreaBottom*<br/>
弄当函数返回时，包含 (在底部选项卡区域的工作区坐标) 中的大小和位置。

### <a name="remarks"></a>备注

框架调用此方法来确定停靠到目标窗格的类型。 当框架确定用户将面板拖动到 "目标" 窗格的选项卡区域上时，它会尝试将第一个窗格添加为 "目标" 窗格的新选项卡。 否则，它会尝试将第一个窗格停靠在目标窗格的相应侧。 框架将使用滑块创建一个新容器，以容纳附加的停靠窗格。

如果 outlook 栏是静态的，则的默认实现将 `GetTabArea` 返回 outlook 栏的整个客户端区域，即，如果 outlook 栏无法浮动。 否则，它将返回页面按钮在 Outlook bar 控件的顶部和底部所采用的区域。

在从派生的类中重写此方法 `CMFCOutlookBar` 以更改此行为。

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a> CMFCOutlookBar：： IsMode2003

指定 Outlook 栏的行为是否模拟 Microsoft Office Outlook 2003 的行为。

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>返回值

如果 Outlook 栏在 Microsoft Office 2003 模式下运行，则为非零值;否则为0。

### <a name="remarks"></a>备注

可以通过使用 [CMFCOutlookBar：： SetMode2003](#setmode2003)启用此模式。

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a> CMFCOutlookBar：： OnAfterAnimation

使用动画设置活动选项卡后，由 [CMFCOutlookBarTabCtrl：： SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 调用。

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>parameters

*nPage*<br/>
中已激活的选项卡页的从零开始的索引。

### <a name="remarks"></a>备注

设置活动选项卡的视觉效果取决于是否已启用动画。 有关详细信息，请参阅 [CMFCOutlookBarTabCtrl：： EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation)。

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a> CMFCOutlookBar：： OnBeforeAnimation

在选项卡页通过使用动画设置为活动选项卡之前，由 [CMFCOutlookBarTabCtrl：： SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) 调用。

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>parameters

*nPage*<br/>
中要设置为活动状态的选项卡页的从零开始的索引。

### <a name="return-value"></a>返回值

如果在设置新的活动选项卡时应使用动画，则返回 TRUE; 如果应禁用动画，则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a> CMFCOutlookBar：： OnScroll

如果 Outlook 面板向上或向下滚动，则由框架调用。

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>parameters

*bDown*<br/>
中如果为 TRUE，则为 TRUE; 否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a> CMFCOutlookBar：： RemoveCustomPage

删除自定义 Outlook 栏选项卡页。

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>parameters

*uiPage*<br/>
中父 Outlook 窗口中的页的从零开始的索引。

*pTargetWnd*<br/>
中Pointerto 父 Outlook 窗口。

### <a name="return-value"></a>返回值

如果已成功删除自定义页，则为非零;否则为0。

### <a name="remarks"></a>备注

调用此函数可删除自定义页。 删除页面后，其控制 ID 将返回到可用 Id 的池。

您必须提供指向 [CMFCOutlookBarTabCtrl 类](../../mfc/reference/cmfcoutlookbartabctrl-class.md) 对象的指针，其中要删除的当前所在的页。 请注意，用户可以在不同的 Outlook 条形之间移动可分离的页，但是有关自定义页的信息驻留在你为其调用了 [CMFCOutlookBar：： CreateCustomPage](#createcustompage)的 Outlook bar 对象中。

使用 [CBaseTabbedPane：： GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) 获取指向 Outlook 窗口的指针。

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a> CMFCOutlookBar：： SetButtonsFont

设置 Outlook 栏按钮上文本的字体。

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>parameters

*pFont*<br/>
中指定新字体。

*bRedraw*<br/>
中如果为 TRUE，则将重绘 Outlook bar。

### <a name="remarks"></a>备注

使用此方法为 outlook 选项卡页面按钮上显示的文本设置字体。

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a> CMFCOutlookBar：： SetMode2003

指定 Outlook 栏的行为是否模仿 Outlook 2003 的行为。

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>parameters

*bMode2003*<br/>
中如果为 TRUE，则启用 Office 2003 模式。

### <a name="remarks"></a>备注

使用此函数可以启用或禁用 Office 2003 模式。 在此模式下，Outlook 栏具有一个带有自定义按钮的附加工具栏。 Outlook 栏的行为与 Microsoft Office 2003 中 Outlook 栏的行为一致。

默认情况下，此模式处于禁用状态。

> [!NOTE]
> 必须先调用此函数，然后才能 [CMFCOutlookBar：： Create](#create)。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CBaseTabbedPane 类](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBarTabCtrl 类](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[CMFCOutlookBarPane 类](../../mfc/reference/cmfcoutlookbarpane-class.md)
