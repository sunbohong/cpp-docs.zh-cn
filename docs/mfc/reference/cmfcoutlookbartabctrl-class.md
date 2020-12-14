---
description: 了解详细信息： CMFCOutlookBarTabCtrl 类
title: CMFCOutlookBarTabCtrl Class
ms.date: 10/18/2018
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
ms.openlocfilehash: b969fbb592fc3098dc8d287004fab90da6f30111
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333501"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

在 Microsoft Outlook 中具有 **“导航窗格”** 可视外观的选项卡控件。
有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|默认构造函数。|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl：： AddControl](#addcontrol)|将 Windows 控件作为新选项卡添加到 Outlook 栏中。|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|由框架调用，用于确定当用户重命名选项卡时显示的编辑框的尺寸。 (重写 `CMFCBaseTabCtrl::CalcRectEdit` 。 ) |
|[CMFCOutlookBarTabCtrl：： CanShowFewerPageButtons](#canshowfewerpagebuttons)|在调整大小操作过程中由框架调用，以确定是否可以显示较少的 Outlook 面板选项卡页按钮（当前可见）。|
|[CMFCOutlookBarTabCtrl：： CanShowMorePageButtons](#canshowmorepagebuttons)|在调整大小操作过程中由框架调用，以确定是否可以显示更多 Outlook 面板选项卡页按钮（当前可见）。|
|[CMFCOutlookBarTabCtrl：： Create](#create)|创建 Outlook 栏选项卡控件。|
|`CMFCOutlookBarTabCtrl::CreateObject`|由框架用于创建此类类型的动态实例。|
|[CMFCOutlookBarTabCtrl：： EnableAnimation](#enableanimation)|指定是否启用在活动选项卡之间切换时发生的动画。|
|[CMFCOutlookBarTabCtrl：： EnableInPlaceEdit](#enableinplaceedit)|指定用户是否可以修改 Outlook 栏的选项卡按钮上的文本标签。  (重写 [CMFCBaseTabCtrl：： EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit)。 ) |
|[CMFCOutlookBarTabCtrl：： EnableScrollButtons](#enablescrollbuttons)|由框架调用，以启用允许用户滚动浏览 Outlook 栏窗格上的按钮的按钮。|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|标识包含指定点的窗格。  (重写 [CMFCBaseTabCtrl：： FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd)。 ) |
|[CMFCOutlookBarTabCtrl：： GetBorderSize](#getbordersize)|返回 Outlook 选项卡控件的边框大小。|
|`CMFCOutlookBarTabCtrl::GetTabArea`|检索选项卡控件的选项卡区域的大小和位置。  (重写 [CMFCBaseTabCtrl：： GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea)。 ) |
|`CMFCOutlookBarTabCtrl::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCOutlookBarTabCtrl：： GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl：： IsAnimation](#isanimation)|确定在活动选项卡之间切换时是否启用动画。|
|[CMFCOutlookBarTabCtrl：： IsMode2003](#ismode2003)|确定 Outlook 栏选项卡控件是否处于模拟 Microsoft Outlook 2003 的模式下。|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|确定某个点是否在选项卡区域内。  (重写 [CMFCBaseTabCtrl：： IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea)。 ) |
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|确定选项卡是否可分离。  (重写 [CMFCBaseTabCtrl：： IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable)。 ) |
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|当插入或删除选项卡时由框架调用。 （重写 `CMFCBaseTabCtrl::OnChangeTabs`。）|
|[CMFCOutlookBarTabCtrl：： OnShowFewerPageButtons](#onshowfewerpagebuttons)|由框架调用以减少可见的选项卡页按钮的数量。|
|[CMFCOutlookBarTabCtrl：： OnShowMorePageButtons](#onshowmorepagebuttons)|由框架调用以增加可见的选项卡页按钮的数量。|
|[CMFCOutlookBarTabCtrl：： OnShowOptions](#onshowoptions)|显示 **导航窗格** 的 "选项" 对话框。|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|重新计算选项卡控件的内部布局。  (重写 [CMFCBaseTabCtrl：： RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout)。 ) |
|[CMFCOutlookBarTabCtrl：： SetActiveTab](#setactivetab)|设置活动选项卡。 (重写 [CMFCBaseTabCtrl：： SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab)。 ) |
|[CMFCOutlookBarTabCtrl：： SetBorderSize](#setbordersize)|设置 Outlook 选项卡控件的边框大小。|
|[CMFCOutlookBarTabCtrl：： SetPageButtonTextAlign](#setpagebuttontextalign)|设置 Outlook 栏的选项卡按钮上的文本标签对齐方式。|
|[CMFCOutlookBarTabCtrl：： SetToolbarImageList](#settoolbarimagelist)|设置包含 Outlook 2003 模式下的 Outlook 栏底部显示的图标的位图 (参阅 [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md)) 。|
|[CMFCOutlookBarTabCtrl：： SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>备注

若要创建具有停靠支持的 Outlook 面板，请使用 `CMFCOutlookBar` 对象承载 "outlook 面板" 选项卡控件。 有关详细信息，请参阅 [CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md)。

## <a name="example"></a>示例

下面的示例演示如何初始化 `CMFCOutlookBarTabCtrl` 对象并使用类中的各种方法 `CMFCOutlookBarTabCtrl` 。 该示例演示如何在 Outlook 栏的选项卡页按钮上启用文本标签的就地编辑，启用动画，启用滚动图柄，使用户能够滚动浏览 Outlook 栏窗格上的按钮，设置 Outlook 选项卡控件的边框大小，并设置 Outlook 栏的选项卡按钮上的文本标签对齐方式。 此代码片段是 [Outlook 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>要求

**标头：** afxoutlookbartabctrl

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a> CMFCOutlookBarTabCtrl：： AddControl

将 Windows 控件作为新选项卡添加到 Outlook 栏中。

```cpp
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>parameters

*pWndCtrl*<br/>
中指向要添加的控件的指针。

*lpszName*<br/>
中指定选项卡的名称。

*bDetachable*<br/>
中如果为 TRUE，则将页面创建为可分离。

*nImageID*<br/>
中显示在 "新建" 选项卡中的图像的 "内部图像" 列表中的图像索引。

*dwControlBarStyle*<br/>
中为包装的停靠窗格指定 AFX_ CBRS_ * 样式。

### <a name="remarks"></a>备注

使用此函数将控件添加为 outlook 条形图的新页。

此函数在 [CMFCBaseTabCtrl：： AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)上的内部调用。

如果将 *bDetachable* 设置为 TRUE，则将 `AddControl` 在内部创建 `CDockablePaneAdapter` 对象并包装添加的控件。 它自动将选项卡式窗口的运行时类设置为的运行时类 `CMFCOutlookBar` 以及浮动框架的运行时类 `CMultiPaneFrameWnd` 。

### <a name="example"></a>示例

下面的示例演示如何使用 `AddControl` 类中的方法 `CMFCOutlookBarTabCtrl` 。 此代码片段是 [Outlook 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl：： CanShowFewerPageButtons

在调整大小操作过程中由框架调用，以确定是否可以显示较少的 Outlook 面板选项卡页按钮（当前可见）。

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>返回值

如果有多个按钮，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

"Outlook 栏" 选项卡控件根据可用空间，动态添加或删除显示的选项卡。 此方法由框架用于在该过程中提供帮助。

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl：： CanShowMorePageButtons

在调整大小操作过程中由框架调用，以确定是否可以显示更多 Outlook 面板选项卡页按钮是否显示为当前可见。

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>返回值

如果存在当前不可见的按钮，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

"Outlook 栏" 选项卡控件根据可用空间，动态添加或删除显示器中的选项卡。 此方法由框架用于在该过程中提供帮助。

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a> CMFCOutlookBarTabCtrl：： Create

创建 Outlook 栏选项卡控件。

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>parameters

*rect*<br/>
中指定初始大小和位置（以像素为单位）。

*pParentWnd*<br/>
中指向父窗口。 不得为 NULL。

*nID*<br/>
中控件 ID。

### <a name="return-value"></a>返回值

如果已成功创建控件，则为非零值;否则为0。

### <a name="remarks"></a>备注

通常，当 [CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md) 控制进程的 WM_CREATE 消息时，将创建 outlook 栏选项卡控件。

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a> CMFCOutlookBarTabCtrl：： EnableAnimation

指定是否启用在活动选项卡之间切换时发生的动画。

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中指定是否应启用或禁用动画。

### <a name="remarks"></a>备注

调用此函数以启用和禁用动画。 当用户打开选项卡页时，如果已启用动画，则页面的标题会向上或向下移动。 如果动画处于禁用状态，则页面会立即变为活动状态。

默认情况下，动画处于启用状态。

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a> CMFCOutlookBarTabCtrl：： EnableInPlaceEdit

指定用户是否可以修改 Outlook 栏的选项卡页按钮上的文本标签。

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
如果为 TRUE，则启用文本标签的就地编辑。 如果为 FALSE，则禁用就地编辑。

### <a name="remarks"></a>备注

调用此函数可在选项卡页按钮上启用或禁用文本标签的就地编辑。 默认情况下，将禁用就地编辑。

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a> CMFCOutlookBarTabCtrl：： EnableScrollButtons

由框架调用，用于启用滚动图柄，使用户能够滚动浏览 Outlook 栏窗格上的按钮。

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中确定是否显示滚动按钮。

*bIsUp*<br/>
中确定是否显示顶部滚动条。

*bIsDown*<br/>
中确定是否显示底部滚动条。

### <a name="remarks"></a>备注

启用滚动按钮的显示。 当活动选项卡更改为还原滚动按钮时，框架会调用此方法。

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a> CMFCOutlookBarTabCtrl：： GetBorderSize

返回 Outlook 选项卡控件的边框大小。

```
int GetBorderSize() const;
```

### <a name="return-value"></a>返回值

边框大小，以像素为单位。

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl：： GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a> CMFCOutlookBarTabCtrl：： IsAnimation

指定是否启用在活动选项卡之间切换时发生的动画。

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>返回值

如果启用动画，则为非零值;否则为0。

### <a name="remarks"></a>备注

调用 [CMFCOutlookBarTabCtrl：： EnableAnimation](#enableanimation) 函数可以启用或禁用动画。

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a> CMFCOutlookBarTabCtrl：： IsMode2003

确定 Outlook 栏选项卡控件是否处于模拟 Microsoft Outlook 2003 的模式下。

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>返回值

如果 Outlook 栏选项卡控件处于 Outlook 2003 模式，则为 TRUE;否则为 FALSE;

### <a name="remarks"></a>备注

此值由 [CMFCOutlookBar：： SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)设置。

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl：： OnShowFewerPageButtons

由框架调用以减少可见的选项卡页按钮的数量。

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>备注

当调整控件大小时，此方法会调整可见页选项卡按钮的数目。

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl：： OnShowMorePageButtons

由框架调用以增加可见的选项卡页按钮的数量。

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>备注

此方法调整调整控件大小时显示的选项卡页按钮的数量。

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a> CMFCOutlookBarTabCtrl：： OnShowOptions

显示 " **导航窗格选项** " 对话框。

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>备注

" **导航窗格选项** " 对话框允许用户选择要显示的选项卡页按钮，以及显示它们的顺序。

当用户从控件的自定义项菜单中选择 **导航窗格选项** 菜单项时，框架会调用此方法。

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a> CMFCOutlookBarTabCtrl：： SetActiveTab

设置 "活动" 选项卡。活动选项卡是打开的选项卡，其内容可见。

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>parameters

*iTab*<br/>
中要打开的选项卡的从零开始的索引。

### <a name="return-value"></a>返回值

如果已成功打开指定选项卡，则为非零值;否则为0。

### <a name="remarks"></a>备注

设置活动选项卡的视觉效果取决于是否已启用动画。 有关详细信息，请参阅 [CMFCOutlookBarTabCtrl：： EnableAnimation](#enableanimation)。

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a> CMFCOutlookBarTabCtrl：： SetBorderSize

设置 Outlook 选项卡控件的边框大小。

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>parameters

*nBorderSize*<br/>
中以像素为单位指定新边框大小。

### <a name="remarks"></a>备注

设置新的边框大小并重新计算 outlook 窗口布局。

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a> CMFCOutlookBarTabCtrl：： SetPageButtonTextAlign

设置 Outlook 栏的选项卡按钮上的文本标签对齐方式。

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>parameters

*uiAlign*<br/>
中指定文本对齐方式。

*bRedraw*<br/>
中如果为 TRUE，则将重绘 outlook 窗口。

### <a name="remarks"></a>备注

使用此函数可以更改页按钮的文本对齐方式。

*uiAlign* 可以是下列值之一：

|返回的常量|含义|
|--------------|-------------|
|TA_LEFT|左对齐|
|TA_CENTER|居中对齐|
|TA_RIGHT|右对齐|

默认值为 TA_CENTER。

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a> CMFCOutlookBarTabCtrl：： SetToolbarImageList

设置包含 outlook 2003 模式下 Outlook 栏底部显示的图标的位图。

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>parameters

*uiID*<br/>
中指定要加载的映像的资源 ID。

*cx*<br/>
中指定图像列表中图像的宽度（以像素为单位）。

*clrTransp*<br/>
中指定透明颜色的 RGB 值。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE;否则，返回 FALSE。

### <a name="remarks"></a>备注

使用此函数可在 Microsoft Office 2003 模式下附加其图像将显示在工具栏按钮上的图像列表。 图像索引应对应于页索引。

如果未处于 Microsoft Office 2003 模式，则不应调用此方法。 有关详细信息，请参阅 [CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md)。

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl：： SetVisiblePageButtons

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>parameters

中 *nVisiblePageButtons*<br/>

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl 类](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarPane 类](../../mfc/reference/cmfcoutlookbarpane-class.md)
