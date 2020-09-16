---
title: CTabbedPane 类
ms.date: 11/04/2016
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
ms.openlocfilehash: cfc0a3099b1d5ff9bd1093cc911745bd61cde64c
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686634"
---
# <a name="ctabbedpane-class"></a>CTabbedPane 类

利用可拆分的选项卡实现窗格的功能。

或更多详细信息，请参阅 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|默认构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)| (重写 [CBaseTabbedPane：:D etachpane](../../mfc/reference/cbasetabbedpane-class.md#detachpane)。 ) |
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|启用或禁用自动选项卡着色。|
|[CTabbedPane::FloatTab](#floattab)|浮动一个窗格，但仅当该窗格当前驻留在可分离选项卡中时。 (重写 [CBaseTabbedPane：： FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)。 ) |
|[CTabbedPane::GetTabArea](#gettabarea)|返回选项卡区域在选项卡式窗口中的大小和位置。|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|确定选项卡式窗格是否可以切换为自动隐藏模式。  (重写 [CBaseTabbedPane：： HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode)。 ) |
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|确定选项卡是否位于窗口的底部。|
|[CTabbedPane::ResetTabs](#resettabs)|将所有选项卡式窗格重置为默认状态。|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|设置可以在自动颜色功能启用时可用的自定义颜色列表。|

### <a name="data-members"></a>数据成员

|“属性”|描述|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|选项卡在应用程序中的的默认位置。|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|自定义 `CMFCTabCtrl`-派生对象的运行时类信息。|

## <a name="remarks"></a>备注

当用户通过将一个窗格指向第二个窗格的标题的方式来附加到另一个窗格，框架自动创建此类的实例。 由框架创建的所有选项卡式窗格都具有值为 -1 的 ID。

若要指定常规选项卡而不是 Outlook 样式选项卡，请将 AFX_CBRS_REGULAR_TABS 样式传递给 [CDockablePane：： CreateEx](../../mfc/reference/cdockablepane-class.md#createex) 方法。

如果你使用可拆离的选项卡创建一个选项卡式窗格，该窗格可能会被框架自动销毁，因此，你不应该存储该指针。 若要获取对选项卡式窗格的指针，请调用 `CBasePane::GetParentTabbedPane` 方法。

## <a name="examples"></a>示例

我们在此示例中创建了一个 `CTabbedPane` 对象。 接下来，使用 [CBaseTabbedPane：： AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) 附加其他选项卡。

```cpp
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),
    TRUE,
    (UINT) -1,
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |
    WS_CLIPCHILDREN | CBRS_LEFT |
    CBRS_FLOAT_MULTI))
{
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create
}

pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```

创建选项卡式控件条形对象的另一种方法是使用 [CDockablePane：： AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd)。 `AttachToTabWnd`方法使用[CDockablePane：： SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)设置的运行时类信息动态创建选项卡式窗格对象。

在此示例中，我们动态地创建了一个选项卡式窗格，附加这两个选项卡，并使第二个选项不可拆离。

```cpp
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>要求

**标头：** afxTabbedPane

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a> CTabbedPane：:D etachPane

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>参数

中 *pBar*<br/>

中 *bHide*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a> CTabbedPane::EnableTabAutoColor

启用或禁用自动选项卡着色。

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>参数

*bEnable*<br/>
中若要启用选项卡的自动着色，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

使用此静态方法可以启用或禁用应用程序的所有选项卡式窗格中的选项卡的自动着色。 启用此功能后，每个选项卡都由其自己的颜色填充。 可以通过调用 [CMFCBaseTabCtrl：： GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) 方法查找用于为选项卡着色的颜色列表。

可以通过调用 [CTabbedPane：： SetTabAutoColors](#settabautocolors)指定将用于选项卡的颜色列表。

默认情况下禁用此选项。

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a> CTabbedPane::FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>参数

中 *pBar*<br/>
中 *nTabID*<br/>
中 *dockMethod*<br/>
中 *bHide*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a> CTabbedPane::GetTabArea

返回选项卡区域在选项卡式窗口中的大小和位置。

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>参数

*rectTabAreaTop*<br/>
弄包含顶部选项卡区域的大小和位置（以屏幕坐标表示）。

*rectTabAreaBottom*<br/>
弄包含底部选项卡区域的大小和位置（以屏幕坐标表示）。

### <a name="remarks"></a>备注

框架调用此方法来确定如何停靠用户正在拖动的窗格。 当用户将窗格拖动到 "目标" 窗格的选项卡区域上方时，框架会尝试将其添加为 "目标" 窗格的新选项卡。 否则，它会尝试将窗格停靠到 "目标" 窗格的一侧，这涉及到创建新的窗格容器，其中包含分隔两个窗格的窗格分隔线。

在派生类中重写此方法 `CTabbedPane` 以更改此行为。

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a> CTabbedPane::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a> CTabbedPane::HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a> CTabbedPane::IsTabLocationBottom

确定选项卡是否位于窗口的底部。

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>返回值

如果选项卡区域位于选项卡式窗口的底部，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a> CTabbedPane：： m_bTabsAlwaysTop

选项卡在应用程序中的的默认位置。

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>备注

将此静态成员设置为 TRUE 可强制在选项卡式窗格的顶部显示应用程序中的所有选项卡。

必须在创建选项卡式窗格之前设置此值。

默认值是 FALSE。

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a> CTabbedPane：： m_pTabWndRTC

自定义 `CMFCTabCtrl`-派生对象的运行时类信息。

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>备注

`CMFCTabCtrl`如果在选项卡式窗格中使用自定义选项卡式窗口，则将此静态成员变量设置为指向派生对象的运行时类信息的指针。

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a> CTabbedPane::ResetTabs

将所有选项卡式窗格重置为默认状态。

```
static void ResetTabs();
```

### <a name="remarks"></a>备注

调用此方法可将所有选项卡式窗格恢复为其默认状态。 调用时，此方法将重置所有选项卡式窗格的边框大小和自动颜色状态。

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a> CTabbedPane::SetTabAutoColors

设置在启用自动颜色功能时使用的自定义颜色的列表。

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>参数

*arColors*<br/>
中包含要设置的颜色的数组。

### <a name="remarks"></a>备注

使用此方法可以自定义启用自动颜色功能时所使用的颜色列表。 这是一个静态函数，它会影响应用程序中的所有选项卡式窗格。

使用 [CTabbedPane：： EnableTabAutoColor](#enabletabautocolor) 可以启用或禁用自动颜色功能。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane 类](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane 类](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md)
