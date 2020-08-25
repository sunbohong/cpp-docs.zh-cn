---
title: AFX 消息
ms.date: 11/04/2016
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
ms.openlocfilehash: 409760eff6ba6b31413c11fb45ea91a6d07b9485
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832394"
---
# <a name="afx-messages"></a>AFX 消息

这些消息在 MFC 中使用。

## <a name="messages"></a>消息

下表列出了在 MFC 库中使用的消息：

|Message|说明|中 *wParam*|*lParam* (所有参数均为 [in]，除非另行说明。 ) |返回值|
|-|-|-|-|-|
|AFX_WM_ACCGETOBJECT|未使用。|未使用。|不适用。|不适用。|
|AFX_WM_ACCGETSTATE|用于辅助功能支持。 将此消息发送到 `CMFCPopupMenu` 或 `CMFCRibbonPanelMenu` 以检索当前元素的状态。|元素的索引，可以是菜单按钮或分隔符。|未使用。|元素状态。 如果索引无效，则为-1; 如果菜单按钮没有特殊属性，则为0。 否则，它是以下标志的组合：<br /><br /> TBBS_DISABLED-已禁用项<br /><br /> TBBS_CHECKED-已选中项<br /><br /> TBBS_BUTTON-该项目是标准按钮<br /><br /> TBBS_PRESSED —按钮已按下<br /><br /> TBBS_INDETERMINATE-未定义状态<br /><br /> TBBS_SEPARATOR-而不是菜单按钮，此元素构成其他菜单项之间的分隔|
|AFX_WM_CHANGE_ACTIVE_TAB|框架将此消息发送到可调整大小的控件条控件。 处理此消息，以便 `CMFCTabCtrl` 在用户更改活动选项卡时接收来自对象的通知。|选项卡的索引。|未使用。|非零.|
|AFX_WM_CHANGE_CURRENT_FOLDER|`CMFCShellListCtrl`当用户已更改当前文件夹时，框架会将此消息发送到的父项。|未使用。|未使用。|未使用。|
|AFX_WM_CHANGEVISUALMANAGER|当用户更改当前的视觉对象管理器时，框架会将此消息发送到所有框架窗口。 在此消息中，框架窗口会重新计算其区域，并根据需要调整其他参数。 如果需要获得有关此事件的通知，可以在应用程序中处理 AFX_WM_CHANGEVISUALMANAGER 消息。 必须 () 调用基类处理程序 `OnChangeVisualManager` ，以确保框架对此事件的内部处理发生。|未使用。|未使用。|未使用。|
|AFX_WM_CHANGING_ACTIVE_TAB|发送到对象的父 `CMFCTabCtrl` 对象。  如果希望 `CMFCTabCtrl` 在用户重置选项卡时接收来自对象的通知，请处理此消息。|正在激活的选项卡的索引。|未使用。|非零.|
|AFX_WM_CHECKEMPTYMINIFRAME|仅限内部使用。|不适用。|不适用。|不适用。|
|AFX_WM_CREATETOOLBAR|`CMFCToolBarsListPropertyPage`当用户在自定义过程中创建新工具栏时发送。 可以通过处理此消息来实例化自定义的 CMFCToolBar 派生对象。 如果处理此消息并创建自己的工具栏，则忽略对默认处理程序的调用。|未使用。|指向包含工具栏名称的字符串的指针。|指向新创建的工具栏的指针。 NULL 表示工具栏创建已取消。|
|AFX_WM_CUSTOMIZEHELP|`CMFCToolbarCustomize Dialog`当用户按 "**帮助**" 按钮或按 F1 键时，从自定义属性表发送到主框架窗口。|指定自定义属性表的活动页。|一个指向 `CMFCToolbarCustomize Dialog` 对象的指针。|Zero。|
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog`发送此消息以通知父框架用户正在创建新的工具栏。|自定义开始时为 TRUE，自定义完成时为 FALSE。|未使用。|Zero。|
|AFX_WM_DELETETOOLBAR|当用户要在自定义模式下删除工具栏时发送到主框架窗口。<br /><br /> 当用户在自定义模式下删除工具栏时，处理此消息以执行其他操作。 还应) 删除工具栏 (的默认处理程序 `OnToolbarDelete` 。 默认处理程序将返回一个值，该值指示是否可以删除工具栏。|未使用。|指向 `CMFCToolBar` 要删除的对象的指针。|如果无法删除工具栏，则为非零值;否则为0。|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` 将此消息发送到主框架窗口以检索文档颜色。|未使用。|[in，out]指向对象的指针 `CList<COLORREF, COLORREF>` 。|Zero。|
|AFX_WM_GETDRAGBOUNDS|仅限内部使用。|不适用。|不适用。|不适用。|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|当用户突出显示功能区列表项时发送到主框架窗口。|突出显示项的索引|指向 `CMFCBaseRibbonElement`|未使用。|
|AFX_WM_ON_AFTER_SHELL_COMMAND|`CMFCShellListCtrl` `CMFCShellTreeCtrl` 当用户完成 shell 命令的执行时，发送到或控件的父级。|用户执行的命令的 ID|未使用。|如果应用程序处理此消息，则它应返回零。|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|在显示弹出菜单之前，框架会将此消息发送到功能区的父级。 您可以随时处理此消息和修改弹出菜单。|未使用。|指向 `CMFCBaseRibbonElement`|未使用。|
|AFX_WM_ON_CANCELTABMOVE|仅限内部使用。|不适用。|不适用。||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|当用户更改活动功能区控件类别时，框架会将此消息发送到主框架。|未使用。|一个指针， `CMFCRibbonBar` 它的类型已更改。|未使用。|
|AFX_WM_ON_CLOSEPOPUPWINDOW|该框架将发送此消息，通知所有者 `CMFCDesktopAlertWnd` 即将关闭该窗口。|未使用。|指向对象的指针 `CMFCDesktopAlertWnd` 。|未使用。|
|AFX_WM_ON_DRAGCOMPLETE|仅限内部使用。|不适用。|不适用。|不适用。|
|AFX_WM_ON_GET_TAB_TOOLTIP|如果启用了自定义工具提示，当选项卡窗口将要显示选项卡的工具提示时，发送到主框架窗口。|未使用。|指向结构的指针 `CMFCTabToolTipInfo` 。|未使用。|
|AFX_WM_ON_HSCROLL|发送到可调整大小的控件条控件。 `CMFCTabCtrl`当滚动事件发生在水平滚动条的选项卡式小组件中时，处理此消息以接收来自对象的通知。|低序位字指定一个指示用户滚动请求的滚动条值。  有关更多信息，请参见本主题中后面的表。|未使用。|非零.|
|AFX_WM_ON_MOVE_TAB|当用户将选项卡拖动到新位置时，发送到选项卡式窗口的父级。|位于其原始位置的选项卡的从零开始的索引。|弄新位置中的选项卡的从零开始的索引。|Zero。|
|AFX_WM_ON_MOVETABCOMPLETE|仅限内部使用。|不适用。|不适用。|不适用。|
|AFX_WM_ON_MOVETOTABGROUP|当用户将 MDI 子窗口从一个选项卡式组移到另一个选项卡式组时发送到主框架窗口。|选项卡式窗口的句柄 (`CMFCTabCtrl`) 从中删除了 MDI 子窗口。|弄 (`CMFCTabCtrl` 已插入 MDI 子窗口) 的选项卡式窗口的句柄。|已忽略。|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|`CDockablePane`当用户单击控件栏标题上的 "**关闭**" 按钮时，发送到的父级。|未使用。|指向可停靠的窗格的指针，用户在该窗格上单击 " **关闭** " 按钮。|如果无法关闭窗格，则为 TRUE;否则为 FALSE。|
|AFX_WM_ON_RENAME_TAB|在用户重命名了可编辑选项卡后发送到选项卡式窗口的父级。|已重命名的选项卡的从零开始的索引。|弄指向字符串的指针，该字符串包含新的选项卡名称。|如果应用程序处理此消息，则为非零值;此框架将取消对的调用 `CMFCBaseTabCtrl::SetTabLabel` 。  如果返回零，则 `CMFCBaseTabCtrl::SetTabLabel` 由框架调用。|
|AFX_WM_ON_RIBBON_CUSTOMIZE|当用户开始自定义时发送到父框架。 如果要显示自己的自定义对话框，请处理此消息。|未使用。|指向要自定义的功能区控件的指针。|如果应用程序处理此消息并显示自己的自定义对话框，则为非零值。 如果应用程序返回零，框架将显示内置自定义对话框。|
|AFX_WM_ON_TABGROUPMOUSEMOVE|仅限内部使用。|不适用。|不适用。|不适用。|
|AFX_WM_POSTSETPREVIEWFRAME|发送通知主框架用户已更改打印预览模式|如果为 TRUE，则表示已设置打印预览模式。 FALSE 表示关闭打印预览模式。|未使用。|未使用。|
|AFX_WM_PROPERTY_CHANGED|`CMFCPropertyGridCtrl`当用户更改所选属性的值时，发送给属性网格控件的所有者 () 。|属性列表的控件 ID。|指向属性的指针 (`CMFCPropertyGridProperty` 更改的) 。|未使用。|
|AFX_WM_RESETCONTEXTMENU|当用户在自定义期间重置上下文菜单时发送到主框架窗口。|上下文菜单的资源 ID。|指向当前上下文菜单的指针 `CMFCPopupMenu` 。|未使用。|
|AFX_WM_RESETKEYBOARD|当用户在自定义期间重置所有键盘快捷键时，框架会将此消息发送到主框架窗口。|未使用。|未使用。|未使用。|
|AFX_WM_RESETMENU|在自定义期间用户重置应用程序框菜单时，框架会将此消息发送给菜单所有者 (框架窗口) |菜单资源 ID。|未使用。|未使用。|
|AFX_WM_RESETPROMPT|当用户从工具栏的 "自定义" 对话框重置工具栏时，框架将发送此消息。 默认处理程序将显示一个消息框，询问用户是否要重置工具栏。|未使用。|未使用。|未使用。|
|AFX_WM_RESETTOOLBAR|`CMFCToolBar`当工具栏还原到其原始状态（即从资源加载）时，对象将发送此消息。 处理此消息可重新插入其类派生自的工具栏按钮 `CMFCToolbarButton` 。 有关详细信息，请参阅 `CMFCToolbarComboBoxButton`。|已还原其状态的工具栏的资源 ID。|未使用。|Zero。|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` 当用户单击常规菜单按钮时，对象会将此消息发送给其所有者。 在 `CMFCToolbarMenuButton` 用户单击按钮时，每次用于显示弹出菜单时都要处理此消息。|用于发送消息的按钮的命令 ID。|光标的屏幕坐标。 低序位字指定 x 坐标。 高阶字指定 y 坐标。|未使用。|
|AFX_WM_TOOLBARMENU|当鼠标指针位于窗格的客户端或非工作区中并且用户释放鼠标右键时，发送到主框架窗口。|未使用。|鼠标指针的屏幕坐标。 低序位字指定 x 坐标。 高阶字指定 y 坐标。|如果应用程序处理此消息，则为零;否则为非零值。|
|AFX_WM_UPDATETOOLTIPS|发送给所有 tooltip 所有者，以指示应重新创建其工具提示控件。|应处理此消息的控件类型。 有关可能值的列表，请参阅本主题后面的表。|未使用。|未使用。|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` 用户单击 " **帮助** " 按钮时，会将此消息发送到父框架，也可以通过单击 " **帮助** " 标题按钮或 F1 键进入帮助模式。|未使用。|指向实例的指针 `CMFCWindowsManagerDialog` 。|未使用。|

下表显示 AFX_WM_HSCROLL 方法的 *lParam* 参数的低字值：

|值|含义|
|-|-|
|SB_ENDSCROLL|用户结束滚动。|
|SB_LEFT|用户滚动到左上角。|
|SB_RIGHT|用户向右下方滚动。|
|SB_LINELEFT|用户向左滚动一个单位。|
|SB_LINERIGHT|用户向右滚动一个单位。|
|SB_PAGELEFT|用户向左滚动窗口的宽度。|
|SB_PAGERIGHT|用户向右滚动窗口的宽度。|
|SB_THUMBPOSITION|用户已将滚动框拖 (拇指) 并释放鼠标按钮。 高阶字指示拖动操作结束时滚动框的位置。|
|SB_THUMBTRACK|用户正在拖动滚动框。 在用户释放鼠标按钮之前，将用此值重复发送 AFX_WM_ON_HSCROLL 消息。 高阶字指示滚动框拖动到的位置。|

> [!NOTE]
> 如果 SB_THUMBPOSITION 或 SB_THUMBTRACK 低序位字，则 *lParam* 参数的高序位字指定滚动框的当前位置;否则，不使用此词。

下表列出了 AFX_WM_UPDATETOOLTIPS 消息的 *lParam* 参数的标志值：

|标志|值|
|-|-|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|

## <a name="see-also"></a>另请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)
