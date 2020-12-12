---
description: 了解详细信息： TN024： MFC-Defined 消息和资源
title: TN024：MFC 定义的消息和资源
ms.date: 11/04/2016
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
ms.openlocfilehash: 7ead4d72588b9acae125cbe90be67d1e03230de8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215750"
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024：MFC 定义的消息和资源

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

此注释描述 MFC 所使用的内部 Windows 消息和资源格式。 此信息说明了如何实现框架，并将帮助你调试应用程序。 对于大胆，即使所有这些信息都是正式不受支持的，你也可以使用此信息进行高级实现。

此注释包含 MFC 私有实现详细信息;所有内容在将来可能会更改。 MFC 专用 Windows 消息仅在一个应用程序的范围内是有意义的，但将来会更改以包含系统范围内的消息。

MFC 专用 Windows 消息和资源类型的范围位于 Microsoft Windows 搁置的保留的 "系统" 范围内。 当前未使用范围中的所有数字，将来可以使用范围中的新数字。 可能会更改当前使用的数字。

MFC 专用 Windows 消息在 0x360->0x37F 的范围内。

MFC 私有资源类型在 0xF0->0xFF 的范围内。

**MFC 专用 Windows 消息**

这些 Windows 消息用于代替 c + + 虚拟函数，在这些函数中，窗口对象之间需要相对松散的耦合，而 c + + 虚拟函数不适合。

这些专用 Windows 消息和关联的参数结构在 MFC 专用标头 "AFXPRIV.H" 中声明。H '。 请注意，包括此标头的任何代码都可能依赖于未记录的行为，并且可能会在未来版本的 MFC 中中断。

在极少数情况下，需要处理其中一条消息时，应使用 ON_MESSAGE 消息映射宏，并以通用 LRESULT/WPARAM/LPARAM 格式处理该消息。

**WM_QUERYAFXWNDPROC**

此消息将发送到正在创建的窗口。 这是在创建过程中非常早发送的，它是一种用于确定 WndProc 是否 AfxWndProc 的方法 **。AfxWndProc** 返回1。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用|
|lParam|未使用|
|返回|如果由 **AfxWndProc** 处理，则为1|

**WM_SIZEPARENT**

当调整 (调用的大小时，此消息将由框架窗口发送给其直接子级， `CFrameWnd::OnSize` `CFrameWnd::RecalcLayout` 这将调用 `CWnd::RepositionBars`) 来重新定位框架两侧的控件条。 AFX_SIZEPARENTPARAMS 结构包含父对象的当前可用客户端矩形和一个 HDWP (，该值可能为 NULL) ，可以调用该矩形 `DeferWindowPos` 来最大程度地减少重画。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用|
|lParam|AFX_SIZEPARENTPARAMS 结构的地址|
|返回|未使用 (0) |

如果忽略该消息，则表示窗口不参与布局。

**WM_SETMESSAGESTRING**

此消息将发送到框架窗口，要求它更新状态栏中的消息行。 可以 (中指定字符串 ID 或 LPCSTR，但不能同时指定这两个) 。

| 参数和返回值 | 描述 |
|-|-|
|wParam|字符串 ID (或零) |
|lParam| (字符串的 LPCSTR 或 NULL) |
|返回|未使用 (0) |

**WM_IDLEUPDATECMDUI**

此消息将在空闲时间发送，以实现更新-命令 UI 处理程序的空闲时间更新。 如果窗口 (通常是控制条) 处理消息，则它会创建一个 `CCmdUI` 对象 (或派生类的对象) 并调用 `CCmdUI::DoUpdate` 窗口中的每个 "项"。 这会依次检查命令处理程序链中对象的 ON_UPDATE_COMMAND_UI 处理程序。

| 参数和返回值 | 描述 |
|-|-|
|wParam|BOOL bDisableIfNoHandler|
|lParam|未使用 (0) |
|返回|未使用 (0) |

如果 ON_UPDATE_COMMAND_UI 和 ON_COMMAND 处理程序均不存在，则 *bDisableIfNoHandler* 为非零值以禁用 UI 对象。

**WM_EXITHELPMODE**

此消息将发送到用于 `CFrameWnd` 退出上下文相关帮助模式的。 此消息的接收将终止启动的模式循环 `CFrameWnd::OnContextHelp` 。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用 (0) |
|lParam|未使用 (0) |
|返回|未使用|

**WM_INITIALUPDATE**

此消息会由文档模板发送到框架窗口的所有子体，在这种情况下，它可以安全地执行其初始更新。 它映射到对的调用， `CView::OnInitialUpdate` 但可在其他 `CWnd` 派生类中用于其他的一次性更新。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用 (0) |
|lParam|未使用 (0) |
|返回|未使用 (0) |

**WM_RECALCPARENT**

此消息由视图发送到其父窗口 (通过 `GetParent`) 获取以强制 (通常情况下，父窗口通常会调用 `RecalcLayout`) 。 这适用于 OLE 服务器应用程序，在这种应用程序中，框架需要随着视图的总大小增长而增长。

如果父窗口处理此消息，则它应返回 TRUE，并用新的工作区大小填充 lParam 中传递的矩形。 在将 `CScrollView` 滚动条) 添加到服务器对象处于就地激活状态时，将使用此对象在窗口外 (位置正确地处理滚动条。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用 (0) |
|lParam|LPRECT rectClient，可能为 NULL|
|返回|如果返回新的客户端矩形，则为 TRUE，否则为 FALSE|

**WM_SIZECHILD**

`COleResizeBar` `GetOwner` 当用户使用调整大小控点调整大小调整栏大小时，会通过) 将此消息发送到其所有者窗口 (。 `COleIPFrameWnd` 尝试在用户请求的位置重定位框架窗口时，对此消息作出响应。

相对于包含大小调整栏的框架窗口的客户端坐标中给定的新矩形由 lParam 指向。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用 (0) |
|lParam|LPRECT rectNew|
|返回|未使用 (0) |

**WM_DISABLEMODAL**

此消息将发送到被停用的框架窗口所有的弹出窗口。 框架窗口使用结果来确定是否禁用弹出窗口。

当框架进入模式状态或阻止某些弹出窗口处于禁用状态时，可以使用此功能在弹出窗口中执行特殊处理。 例如，当框架窗口进入模式状态时，工具提示将使用此消息销毁自身。

| 参数和返回值 | 描述 |
|-|-|
|wParam|未使用 (0) |
|lParam|未使用 (0) |
|返回|非零值表示 **不** 禁用窗口，0表示禁用窗口|

**WM_FLOATSTATUS**

当其他顶级框架窗口激活或停用框架窗口时，此消息将发送到框架窗口拥有的所有弹出窗口。 此设置由中 MFS_SYNCACTIVE 的实现使用 `CMiniFrameWnd` ，以使这些弹出窗口与激活顶级框架窗口时保持同步。

| parameters | 说明 |
|-|-|
|wParam|是以下值之一：<br /><br /> FS_SHOW<br /><br /> FS_HIDE<br /><br /> FS_ACTIVATE<br /><br /> FS_DEACTIVATE<br /><br /> FS_ENABLEFS_DISABLE<br /><br /> FS_SYNCACTIVE|
|lParam|未使用 (0) |

如果设置 FS_SYNCACTIVE，并且该窗口将其激活与父框架 syncronizes，则返回值应为非零值。 `CMiniFrameWnd` 如果样式设置为 MFS_SYNCACTIVE，则返回非零值。

有关详细信息，请参阅的实现 `CMiniFrameWnd` 。

## <a name="wm_activatetoplevel"></a>WM_ACTIVATETOPLEVEL

当激活或停用 "顶级组" 中的窗口时，此消息将发送到顶级窗口。 如果某个窗口是顶级窗口 (没有父项或所有者) ，或者它属于此类窗口，则它是顶级组的一部分。 此消息与用于 WM_ACTIVATEAPP 的方式类似，但在以下情况下有效：属于不同进程的 windows 在单个窗口层次结构中混合， (在 OLE 应用程序) 中常见。

## <a name="wm_commandhelp-wm_helphittest-wm_exithelpmode"></a>WM_COMMANDHELP、WM_HELPHITTEST WM_EXITHELPMODE

这些消息用于实现上下文相关帮助。 有关详细信息，请参阅 [技术说明 28](../mfc/tn028-context-sensitive-help-support.md) 。

## <a name="mfc-private-resource-formats"></a>MFC 专用资源格式

目前，MFC 定义两种专用资源格式： RT_TOOLBAR 和 RT_DLGINIT。

## <a name="rt_toolbar-resource-format"></a>RT_TOOLBAR 资源格式

向导向导提供的默认工具栏基于在 MFC 4.0 中引入的 RT_TOOLBAR 自定义资源。 您可以使用工具栏编辑器来编辑此资源。

## <a name="rt_dlginit-resource-format"></a>RT_DLGINIT 资源格式

一个 MFC 专用资源格式用于存储额外的对话框初始化信息。 这包括存储在组合框中的初始字符串。 此资源的格式不是为了手动编辑而设计的，而是由 Visual C++ 处理的。

Visual C++ 和此 RT_DLGINIT 资源不需要使用 MFC 的相关功能，因为存在使用资源中信息的 API 替代方法。 使用 Visual C++ 使你可以更轻松地在长时间运行时写入、维护和转换应用程序。

RT_DLGINIT 资源的基本结构如下所示：

```
+---------------+    \
| Control ID    |   UINT             |
+---------------+    |
| Message #     |   UINT             |
+---------------+    |
|length of data |   DWORD            |
+---------------+    |   Repeated
|   Data        |   Variable Length  |   for each control
|   ...         |   and Format       |   and message
+---------------+    /
|     0         |   BYTE
+---------------+
```

重复节包含要向其发送消息的控件 ID，消息 # 用于发送 (正常的 Windows 消息) 和可变长度的数据。 Windows 消息以下列形式发送：

```
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```

这是一种非常通用的格式，允许任何 Windows 消息和数据内容。 Visual C++ 资源编辑器和 MFC 仅支持有限的 Windows 消息子集： CB_ADDSTRING 用于组合框的初始列表选项， (数据是文本字符串) 。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
