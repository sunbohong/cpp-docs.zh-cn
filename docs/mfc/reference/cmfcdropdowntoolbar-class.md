---
description: 了解详细信息： CMFCDropDownToolBar 类
title: CMFCDropDownToolBar 类
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: 158562829cb5bbebfb9a858d34751c56bdf46ed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293984"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar 类

当用户按住顶层工具栏按钮时显示的工具栏。

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCDropDownToolBar：： AllowShowOnPaneMenu](#allowshowonpanemenu)|（重写 `CPane::AllowShowOnPaneMenu`。）|
|[CMFCDropDownToolBar：： LoadBitmap](#loadbitmap)| (重写 [CMFCToolBar：： LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap)。 ) |
|[CMFCDropDownToolBar：： LoadToolBar](#loadtoolbar)| (重写 [CMFCToolBar：： LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar)。 ) |
|[CMFCDropDownToolBar：： OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar：： OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar：： OnSendCommand](#onsendcommand)|（重写 `CMFCToolBar::OnSendCommand`。）|
|[CMFCDropDownToolBar：： OnUpdateCmdUI](#onupdatecmdui)| (重写 [CMFCToolBar：： OnUpdateCmdUI](cmfctoolbar-class.md)。|

### <a name="remarks"></a>备注

`CMFCDropDownToolBar`对象将工具栏的视觉外观与弹出菜单的行为组合在一起。 当用户按下并按住下拉工具栏按钮时 (参阅 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)) ，此时将显示一个下拉工具栏，用户可以通过滚动到该工具栏并释放鼠标按钮从下拉工具栏中选择一个按钮。 用户选择下拉工具栏中的按钮后，该按钮将显示为顶级工具栏上的 "当前" 按钮。

不能自定义或停靠下拉工具栏，它也不会脱离状态。

下图显示了 `CMFCDropDownToolBar` 对象：

![CMFCDropDownToolbar 示例](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar 示例")

创建 `CMFCDropDownToolBar` 对象的方式与创建普通工具栏 (参阅 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)) 。

若要将下拉工具栏插入父工具栏，请执行以下操作：

1. 在父级工具栏资源中保留该按钮的虚拟资源 ID。

2. 创建一个 `CMFCDropDownToolBarButton` 包含下拉工具栏 (的对象。有关详细信息，请参阅 [CMFCDropDownToolbarButton：： CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)) 。

3. `CMFCDropDownToolBarButton`使用[CMFCToolBar：： ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)将虚拟按钮替换为对象。

有关工具栏按钮的详细信息，请参阅 [演练：将控件放置在工具栏上](../../mfc/walkthrough-putting-controls-on-toolbars.md)。 有关下拉工具栏的示例，请参阅示例项目 VisualStudioDemo。

## <a name="example"></a>示例

下面的示例演示如何使用 `Create` 类中的方法 `CMFCDropDownToolBar` 。 此代码片段是 [Visual Studio 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCDropDownToolBar：： AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a> CMFCDropDownToolBar：： LoadBitmap

从应用程序资源加载工具栏图像。

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>parameters

*uiResID*<br/>
中引用热工具栏图像的位图的资源 ID。

*uiColdResID*<br/>
中用于引用冷工具栏图像的位图的资源 ID。

*uiMenuResID*<br/>
中引用常规菜单图像的位图的资源 ID。

*对方*<br/>
中若要锁定工具栏，则为 TRUE;否则为 FALSE。

*uiDisabledResID*<br/>
中引用禁用工具栏图像的位图的资源 ID。

*uiMenuDisabledResID*<br/>
中引用禁用的菜单图像的位图的资源 ID。

### <a name="return-value"></a>返回值

如果该方法成功，则为非零；否则为零。

### <a name="remarks"></a>备注

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) 方法调用此方法以加载与工具栏关联的图像。 重写此方法以执行图像资源的自定义加载。

调用 `LoadBitmapEx` 方法以在创建工具栏后加载其他图像。

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a> CMFCDropDownToolBar：： LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>parameters

中 *uiResID*<br/>

中 *uiColdResID*<br/>

中 *uiMenuResID*<br/>

中 *BOOL*<br/>

中 *uiDisabledResID*<br/>

中 *uiMenuDisabledResID*<br/>

中 *uiHotResID*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a> CMFCDropDownToolBar：： OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>parameters

中 *nFlags*<br/>

中 *点*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a> CMFCDropDownToolBar：： OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>parameters

中 *nFlags*<br/>

中 *点*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a> CMFCDropDownToolBar：： OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>parameters

中 *pButton*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCDropDownToolBar：： OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>parameters

中 *pTarget*<br/>

中 *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar：： Create](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar：： ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton 类](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[演练：将控件置于工具栏上](../../mfc/walkthrough-putting-controls-on-toolbars.md)
