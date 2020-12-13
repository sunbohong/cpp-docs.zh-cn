---
description: 了解详细信息： CMFCPopupMenuBar 类
title: CMFCPopupMenuBar 类
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: 4db8c02ed92aec5243f9a2c7800c6fd1f9747751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334745"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar 类

嵌入到弹出菜单的菜单栏。

## <a name="syntax"></a>语法

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|立即重新计算窗格的布局。  (重写 [CPane：： AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)。 ) |
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|从指定的菜单资源加载弹出菜单项。|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|关闭延迟的弹出菜单按钮。|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|从弹出菜单按钮生成菜单。|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|定位工具栏，指定点位于该位置。|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|指示菜单按钮图像的大小。|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|返回默认菜单项的标识符。|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|获取最近调用的菜单命令的索引。|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|获取弹出菜单栏的行偏移量。|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|导入指定菜单中的弹出菜单按钮。|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|指示弹出菜单栏是否处于下拉列表模式下。|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|指示弹出菜单栏是否处于调色板模式。|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|指示默认情况下，这是否为功能区面板 (FALSE) 。|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|指示这是否为常规模式下的功能区面板 (默认) 为 FALSE。|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|加载存档的菜单。|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|还原用于关闭弹出菜单栏的延迟菜单按钮。|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|设置给定索引处的工具栏按钮的样式。  (重写 [CMFCToolBar：： SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)。 ) |
|[CMFCPopupMenuBar::SetOffset](#setoffset)|设置弹出菜单栏的行偏移量。|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|启动指定延迟的弹出菜单按钮的计时器。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCPopupMenuBar：： m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|指定当应用程序具有 Windows XP 外观时是否显示灰色栏。|

## <a name="remarks"></a>备注

`CMFCPopupMenuBar`同时创建[CMFCPopupMenu 类](../../mfc/reference/cmfcpopupmenu-class.md)并将其嵌入其中。 `CMFCPopupMenuBar`涵盖对象的整个工作区 `CMFCPopupMenu` 。 它支持键盘和鼠标输入。 它还将该输入传达给 `CMFCPopupMenu` 和顶级框架窗口。

## <a name="example"></a>示例

下面的示例演示如何 `CMFCPopupMenuBar` 从对象中初始化对象 `CMFCPopupMenu` 。 此代码片段属于 [Draw Client 示例](../../overview/visual-cpp-samples.md)。

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>要求

**标头：** afxpopupmenubar

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a> CMFCPopupMenuBar：： AdjustSizeImmediate

立即重新计算弹出菜单栏窗格的布局。  (重写 [CPane：： AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)。

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>parameters

*bRecalcLayout*<br/>
中如果为 TRUE，则自动重新计算弹出菜单栏窗格的布局;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a> CMFCPopupMenuBar：： BuildOrigItems

从指定的菜单资源加载弹出菜单项。

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>parameters

*uiMenuResID*<br/>
中指定要加载的菜单资源的菜单 ID。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a> CMFCPopupMenuBar：： CloseDelayedSubMenu

关闭已延迟的弹出菜单按钮。

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a> CMFCPopupMenuBar：： ExportToMenu

从弹出菜单按钮生成菜单。

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>返回值

返回新菜单的句柄。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a> CMFCPopupMenuBar：： FindDestintationToolBar

定位工具栏，指定点位于该位置。

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>parameters

*情况*<br/>
中屏幕上的一个点。

### <a name="return-value"></a>返回值

返回指向某个点所在的工具栏的句柄（如果有），如果没有，则返回 NULL。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a> CMFCPopupMenuBar：： GetCurrentMenuImageSize

指示菜单按钮图像的大小。

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>返回值

返回工具栏中菜单按钮图像的大小。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a> CMFCPopupMenuBar：： GetDefaultMenuId

返回默认菜单项的标识符。

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>返回值

返回弹出菜单栏中的默认菜单项的标识符。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a> CMFCPopupMenuBar：： GetLastCommandIndex

获取最近调用的菜单命令的索引。

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>返回值

返回已调用的最后一个菜单命令的索引。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a> CMFCPopupMenuBar：： GetOffset

获取弹出菜单栏的行偏移量。

```
int GetOffset() const;
```

### <a name="return-value"></a>返回值

返回弹出菜单栏的行偏移量。

### <a name="remarks"></a>备注

此值是使用 [CMFCPopupMenuBar：： SetOffset](#setoffset)设置的。

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a> CMFCPopupMenuBar：： ImportFromMenu

导入指定菜单中的弹出菜单按钮。

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>parameters

*hMenu*<br/>
中要从中导入弹出菜单按钮的菜单。

*bShowAllCommands*<br/>
中如果要导入菜单上的所有命令，则为 TRUE; 如果很少使用，则可能隐藏。

### <a name="return-value"></a>返回值

如果菜单按钮已成功从菜单导入，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a> CMFCPopupMenuBar：： IsDropDownListMode

指示弹出菜单栏是否处于下拉列表模式下。

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>返回值

如果弹出菜单栏处于下拉列表模式，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a> CMFCPopupMenuBar：： IsPaletteMode

指示弹出菜单栏是否处于调色板模式。

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>返回值

如果启用了调色板模式，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

当菜单栏设置为调色板模式时，菜单项显示在多个列中，行数仅限。

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a> CMFCPopupMenuBar：： IsRibbonPanel

指示默认情况下，这是否为功能区面板 (FALSE) 。

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>返回值

默认情况下，返回 FALSE，指示这不是功能区面板。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a> CMFCPopupMenuBar：： IsRibbonPanelInRegularMode

指示这是否为常规模式下的功能区面板 (默认) 为 FALSE。

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>返回值

默认情况下，返回 FALSE，指示这不是常规模式下的功能区面板。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a> CMFCPopupMenuBar：： LoadFromHash

加载存档的菜单。

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>parameters

*hMenu*<br/>
中要加载的存档菜单的句柄。

### <a name="return-value"></a>返回值

如果菜单加载成功，则返回 TRUE; 否则返回 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a> CMFCPopupMenuBar：： m_bDisableSideBarInXPMode

一个布尔参数，用于指示当应用程序具有 Windows XP 外观时是否具有灰色边栏。

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>备注

如果此成员变量设置为 FALSE，并且你的应用程序具有 Windows XP 外观，则框架将在你的应用程序中绘制一个灰色的边栏。

默认值是 FALSE。

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a> CMFCPopupMenuBar：： RestoreDelayedSubMenu

还原用于关闭弹出菜单栏的延迟菜单按钮。

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a> CMFCPopupMenuBar：： SetButtonStyle

设置给定索引处的工具栏按钮的样式。  (重写 [CMFCToolBar：： SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)。 ) 

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中要设置其样式的工具栏按钮的从零开始的索引。

*nStyle*<br/>
中按钮的样式。 有关可用工具栏按钮样式的列表，请参阅 [Toolbar 控件样式](../../mfc/reference/toolbar-control-styles.md) 。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a> CMFCPopupMenuBar：： SetOffset

设置弹出菜单栏的行偏移量。

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>parameters

*iOffset*<br/>
中弹出菜单栏应偏移的行数。

### <a name="remarks"></a>备注

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a> CMFCPopupMenuBar：： StartPopupMenuTimer

启动指定延迟的弹出菜单按钮的计时器。

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>parameters

*pMenuButton*<br/>
中一个指针，指向要为其设置延迟计时器的菜单按钮。

*nDelayFactor*<br/>
中延迟系数（等于至少一个）乘以标准菜单延迟时间， (一般为半秒到5秒) 。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar 类](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopupMenu 类](../../mfc/reference/cmfcpopupmenu-class.md)
