---
description: 了解详细信息： TN021：命令和消息路由
title: TN021：命令和消息传送
ms.date: 06/28/2018
f1_keywords:
- vc.routing
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
ms.openlocfilehash: 3cc481585fa2f1eacc3deb575e163d5a1644002c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215841"
---
# <a name="tn021-command-and-message-routing"></a>TN021：命令和消息传送

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

此注释描述了命令路由和调度体系结构，以及常规窗口消息路由中的高级主题。

请参阅 Visual C++，了解有关此处所述体系结构的一般详细信息，尤其是 Windows 消息、控制通知和命令之间的区别。 此说明假定你非常熟悉打印文档中所述的问题，并且仅处理非常高级的主题。

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>命令路由和调度 MFC 1.0 功能演变为 MFC 2.0 体系结构

Windows 有 WM_COMMAND 的消息，它会重载以提供菜单命令、快捷键和对话控件通知的通知。

MFC 1.0 通过允许命令处理程序 (例如，在派生类中 ) "OnFileNew"， `CWnd` 以响应特定的 WM_COMMAND 来进行调用。 这与一种称为消息映射的数据结构一起粘附在一起，从而产生了一个非常节省空间的命令机制。

MFC 1.0 还提供了其他功能，用于分隔来自命令消息的控件通知。 命令由16位 ID 表示，有时称为命令 ID。 命令通常从 (开始 `CFrameWnd` ，即菜单选择或翻译加速器) 并路由到多种其他窗口。

MFC 1.0 使用命令路由，因为在多个文档界面 (MDI) 的实现中实现了一个有限的意义。  (MDI 框架窗口将命令委托给其活动的 MDI 子窗口。 ) 

此功能已在 MFC 2.0 中通用化和扩展，以允许更大范围的对象处理命令 (不只是) 的窗口对象。 它为路由消息提供更为正式的可扩展体系结构，并重复使用命令目标路由，以便不仅处理命令，而且还用于更新 UI 对象 (例如菜单项和工具栏按钮) 来反映命令的当前可用性。

## <a name="command-ids"></a>命令 ID

有关命令路由和绑定过程的说明，请参阅 Visual C++。 [技术说明 20](../mfc/tn020-id-naming-and-numbering-conventions.md) 包含有关 ID 命名的信息。

对于命令 Id，我们使用一般前缀 "ID_"。 命令 Id >= 0x8000。 如果有 STRINGTABLE 资源与命令 ID 具有相同的 Id，则消息行或状态栏将显示命令描述字符串。

在应用程序的资源中，命令 ID 可以出现在多个位置：

- 在一个与消息行提示符具有相同 ID 的 STRINGTABLE 资源中。

- 可能有许多附加到调用同一命令的菜单项的菜单资源。

-  (GOSUB 命令的对话框按钮中的高级) 。

在应用程序的源代码中，命令 ID 可以出现在多个位置：

- 在资源中。H (或其他主符号头文件) 来定义特定于应用程序的命令 Id。

- 可能在用于创建工具栏的 ID 数组中。

- 在 ON_COMMAND 宏中。

- 可能位于 ON_UPDATE_COMMAND_UI 宏中。

目前，MFC 中需要命令 Id 的唯一实现 >= 0x8000 是 GOSUB 对话框/命令的实现。

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>GOSUB 命令，在对话框中使用命令体系结构

路由和启用命令的命令体系结构适用于框架窗口、菜单项、工具栏按钮、对话框栏按钮、其他控制条和其他用户界面元素，旨在更新按需更新并将命令或控制 Id 路由到主命令目标 (通常是主框架窗口) 。 此主命令目标可以适当地将命令或控件通知路由到其他命令目标对象。

如果将对话框控件的控件 ID 分配给相应的命令 ID，则 (模式或无模式) 的对话框可从命令体系结构的某些功能中受益。 对话框的支持不是自动的，因此你可能需要编写一些附加代码。

请注意，要使所有这些功能正常工作，命令 Id 应该 >= 0x8000。 由于许多对话框可能会路由到同一个帧，因此应将共享命令 >= 0x8000，而特定对话中的非共享 IDCs 应 <= 0x7FFF。

您可以在普通模式对话框中放置一个普通按钮，并将该按钮设置为相应的命令 ID。 当用户选择该按钮时，对话框的所有者通常 (主框架窗口) 获取命令，就像任何其他命令一样。 这称为 GOSUB 命令，因为它通常用于打开) 第一个对话框 (的另一个对话框。

你还可以 `CWnd::UpdateDialogControls` 在对话框中调用函数，并向其传递主框架窗口的地址。 此函数将根据用户是否在框架中具有命令处理程序来启用或禁用对话框控件。 在应用程序的空闲循环中，将自动为你调用此函数，但你必须直接为你希望使用此功能的普通对话框调用此函数。

## <a name="when-on_update_command_ui-is-called"></a>调用 ON_UPDATE_COMMAND_UI 时

始终维护程序的所有菜单项的已启用/选中状态，这可能是一项计算成本高昂的问题。 常见的一种方法是仅在用户选择弹出项时启用/检查菜单项。 MFC 2.0 实现 `CFrameWnd` 处理 WM_INITMENUPOPUP 消息，并使用命令路由体系结构通过 ON_UPDATE_COMMAND_UI 处理程序确定菜单的状态。

`CFrameWnd` 还处理 WM_ENTERIDLE 消息以描述在状态栏上选择的当前菜单项， (也称为 "消息行) "。

应用程序的菜单结构（由 Visual C++ 编辑）用于表示 WM_INITMENUPOPUP 时可用的潜在命令。 ON_UPDATE_COMMAND_UI 处理程序可以修改菜单的状态或文本，或对高级使用 (例如文件 MRU 列表或 OLE 谓词弹出菜单) ，则在绘制菜单之前，实际修改菜单结构。

在应用程序进入其空闲循环) 时，将对工具栏 (和其他控制条执行相同的 ON_UPDATE_COMMAND_UI 处理。 有关控制栏的详细信息，请参阅类库 *参考* 和 [技术说明 31](../mfc/tn031-control-bars.md) 。

## <a name="nested-pop-up-menus"></a>嵌套的弹出菜单

如果你使用的是嵌套菜单结构，你会注意到，弹出菜单中第一个菜单项的 ON_UPDATE_COMMAND_UI 处理程序是在两个不同的情况下调用的。

首先，为弹出菜单本身调用此方法。 这是必需的，因为弹出菜单没有 Id，使用弹出菜单的第一个菜单项的 ID 来引用整个弹出菜单。 在这种情况下，对象的 *m_pSubMenu* 成员变量 `CCmdUI` 将为非 NULL，并将指向弹出菜单。

其次，在弹出菜单中的菜单项被绘制之前调用它。 在这种情况下，该 ID 只引用第一个菜单项，并且该对象的 *m_pSubMenu* 成员变量 `CCmdUI` 将为 NULL。

这允许你启用与菜单项不同的弹出菜单，但需要你编写一些菜单识别代码。 例如，在具有以下结构的嵌套菜单中：

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

可以单独启用或禁用 ID_NEW_SHEET 和 ID_NEW_CHART 命令。 如果启用了这两个中的任一项，则应启用 **新** 的弹出菜单。

弹出) 中的第一个命令 (ID_NEW_SHEET 的命令处理程序如下所示：

```cpp
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)
{
    if (pCmdUI->m_pSubMenu != NULL)
    {
        // enable entire pop-up for "New" sheet and chart
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;
        // CCmdUI::Enable is a no-op for this case, so we
        // must do what it would have done.
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,
            MF_BYPOSITION |
            (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

        return;
    }
    // otherwise just the New Sheet command
    pCmdUI->Enable(m_bCanCreateSheet);
}
```

ID_NEW_CHART 的命令处理程序将是普通的更新命令处理程序，如下所示：

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="on_command-and-on_bn_clicked"></a>ON_COMMAND 和 ON_BN_CLICKED

**ON_COMMAND** 和 **ON_BN_CLICKED** 的消息映射宏是相同的。 MFC 命令和控件通知路由机制仅使用命令 ID 来决定路由到的位置。 控件通知代码为零 (**BN_CLICKED**) 的控件通知被解释为命令。

> [!NOTE]
> 事实上，所有控制通知消息都将通过命令处理程序链。 例如，在技术上，你可以为文档类中的 **EN_CHANGE** 编写控件通知处理程序。 通常不建议这样做，因为此功能的实际应用程序很少，ClassWizard 不支持该功能，并且使用该功能可能会导致代码脆弱。

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>禁用按钮控件的自动禁用

如果将 "按钮" 控件放置在对话框上，或使用您自己调用 **CWnd：： UpdateDialogControls** 的对话框中的按钮，则您会注意到，框架不会自动禁用 **ON_COMMAND** 或 **ON_UPDATE_COMMAND_UI** 处理程序的按钮。 在某些情况下，您不需要处理程序，但您会希望该按钮保持启用状态。 实现此目的的最简单方法是添加一个虚拟命令处理程序， (易于使用 ClassWizard) 并不执行任何操作。

## <a name="window-message-routing"></a>窗口消息路由

下面介绍了有关 MFC 类以及 Windows 消息路由和其他主题对它们的影响的更高级主题。 此处的信息只是简单说明。 有关公共 Api 的详细信息，请参阅 *类库参考* 。 有关实现的详细信息，请参阅 MFC 库源代码。

有关窗口清理的详细信息，请参阅 [技术说明 17](../mfc/tn017-destroying-window-objects.md) ，这是一个非常重要的主题，适用于所有 **CWnd** 派生类。

## <a name="cwnd-issues"></a>CWnd 问题

实现成员函数 **CWnd：： OnChildNotify** 为子 windows (提供强大且可扩展的体系结构，该体系结构也称为控件) 挂钩，或以其他方式通知发送到其父 (或 "所有者" ) 的消息、命令和控件通知。 如果子窗口 (/control) 是 c + + **CWnd** 对象本身，则首先使用原始消息中的参数调用虚拟函数 **OnChildNotify** ， (也就是说， **消息** 结构) 。 子窗口可以仅保留消息、对其进行吃，或修改父 (罕见) 的消息。

默认 **CWnd** 实现处理以下消息，并使用 **OnChildNotify** 挂钩允许子窗口 (控件) 在消息中第一次访问：

- 用于自行绘制的 **WM_MEASUREITEM** 和 **WM_DRAWITEM** () 

- 用于自行绘制的 **WM_COMPAREITEM** 和 **WM_DELETEITEM** () 

- **WM_HSCROLL** 和 **WM_VSCROLL**

- **WM_CTLCOLOR**

- **WM_PARENTNOTIFY**

你会注意到， **OnChildNotify** 挂钩用于将所有者描述消息更改为自绘制消息。

除 **OnChildNotify** 挂钩外，滚动消息还具有进一步的路由行为。 有关 **WM_HSCROLL** 和 **WM_VSCROLL** 消息的滚动条和源的详细信息，请参阅下面的详细信息。

## <a name="cframewnd-issues"></a>CFrameWnd 问题

**CFrameWnd** 类提供大部分命令路由和用户界面更新实现。 这主要用于应用程序的主框架窗口 (**CWinApp：： m_pMainWnd**) 但适用于所有框架窗口。

主框架窗口是带有菜单栏的窗口，是状态栏或消息行的父窗口。 有关命令路由和 WM_INITMENUPOPUP，请参阅上述讨论 **。**

**CFrameWnd** 类提供了活动视图的管理。 将通过活动视图路由以下消息：

- 活动视图 (的所有命令消息将首先获取对它们的访问) 。

- **WM_HSCROLL** 和 **WM_VSCROLL** 来自同级滚动条的消息 (参见下面的 ") "。

- 为 MDI) **WM_ACTIVATE** (和 **WM_MDIACTIVATE** 会转换为对虚拟函数 **CView：： OnActivateView** 的调用。

## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/CMDIChildWnd 问题

这两个 MDI 框架窗口类均派生自 **CFrameWnd** ，因此它们都是为在 **CFrameWnd** 中提供的相同类型的命令路由和用户界面更新而启用的。 在典型的 MDI 应用程序中，只有主框架窗口 (即， **CMDIFrameWnd** 对象) 保存菜单栏和状态栏，因此是命令路由实现的主要来源。

一般的路由方案是活动的 MDI 子窗口首先获取对命令的访问。 默认的 **PreTranslateMessage** 函数同时处理 mdi 子窗口 (第一个) 和 mdi 帧 (第二个) ，以及通常由 **TranslateMDISysAccel** (最后) 处理的标准 MDI 系统命令加速器。

## <a name="scroll-bar-issues"></a>滚动条问题

处理滚动消息 (**WM_HSCROLL** / **OnHScroll** 和/或 **WM_VSCROLL** / **OnVScroll**) 时，应尝试编写处理程序代码，使其不依赖于滚动条消息的来源位置。 这不仅是一个常见的 Windows 问题，而且滚动消息可以来自真正的滚动条控件或来自 / 不是滚动条控件的 WS_HSCROLL **WS_VSCROLL** 滚动条。

MFC 扩展为允许将滚动条控件作为正在滚动的窗口的子节点或同级 (事实上，滚动条和滚动窗口之间的父/子关系可以是任何) 。 这对于带有拆分窗口的共享滚动条尤其重要。 有关 **CSplitterWnd** 实现的详细信息，包括有关共享滚动条问题的详细信息，请参阅 [技术说明 29](../mfc/tn029-splitter-windows.md) 。

在便笺中，有两个 **CWnd** 派生类，在创建时指定的滚动条样式会被捕获，而不会传递到 Windows。 将 **WS_HSCROLL** 和 **WS_VSCROLL** 传递到创建例程后，可以独立设置，但在创建之后无法更改。 当然，您不应直接测试或设置其创建的窗口的 WS_SCROLL 样式位。

对于 **CMDIFrameWnd** ，将使用传递给 **create** 或 **LoadFrame** 的滚动条样式来创建 MDICLIENT。 如果希望将可滚动的 MDICLIENT 区域 (如 Windows 程序管理器) 请务必设置滚动条样式 (**WS_HSCROLL** **&#124; WS_VSCROLL) 用于** 创建 **CMDIFrameWnd** 的样式。

对于 **CSplitterWnd** ，滚动条样式应用于拆分器区域的特殊共享滚动条。 对于静态拆分窗口，通常不会设置滚动条样式。 对于动态拆分窗口，您通常会将滚动条样式设置为要拆分的方向，即 **WS_HSCROLL** 如果可以拆分行， **WS_VSCROLL** 是否可以拆分列。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
