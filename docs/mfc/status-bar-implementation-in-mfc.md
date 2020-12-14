---
description: 了解详细信息： MFC 中的状态栏实现
title: MFC 中的状态栏实现
ms.date: 11/19/2018
f1_keywords:
- COldStatusBar
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
ms.openlocfilehash: d42f8b4bf6ae72cf8eb4a12d1f5eafb8603c5e1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216751"
---
# <a name="status-bar-implementation-in-mfc"></a>MFC 中的状态栏实现

[CStatusBar](../mfc/reference/cstatusbar-class.md)对象是具有一行文本输出窗格的控件条。 输出窗格通常用作消息行和状态指示器。 示例包括菜单帮助-消息行，其中简要说明了所选菜单命令以及显示滚动锁定状态、NUM LOCK 和其他键的指示器。

从 MFC 版本4.0，使用 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)类实现了状态栏，此类可封装状态栏公共控件。 为了向后兼容，MFC 在类中保留了较旧的状态栏实现 `COldStatusBar` 。 更早版本的 MFC 的文档 `COldStatusBar` 在下介绍 `CStatusBar` 。

使用[CStatusBar：： GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl)（MFC 4.0 的一种新成员函数），可以利用 Windows 公共控件对状态栏自定义和其他功能的支持。 `CStatusBar` 成员函数为你带来了 Windows 公共控件的大多数功能;但是，当您调用时 `GetStatusBarCtrl` ，您可以为您的状态栏生成更多的状态栏特征。 调用时 `GetStatusBarCtrl` ，它将返回对对象的引用 `CStatusBarCtrl` 。 您可以使用该引用来操作状态栏控件。

下图显示了一个状态栏，其中显示了多个指示器。

![状态栏](../mfc/media/vc37dy1.gif "状态栏") <br/>
状态栏

与工具栏一样，状态栏对象嵌入在其父框架窗口中，并在构造框架窗口时自动构造。 当父框架被销毁时，状态栏（如所有控件条）也会自动销毁。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [更新状态栏窗格的文本](../mfc/updating-the-text-of-a-status-bar-pane.md)

- MFC 类 [CStatusBar](../mfc/reference/cstatusbar-class.md) 和 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [控件条](../mfc/control-bars.md)

- [对话栏](../mfc/dialog-bars.md)

- [工具栏 (MFC 工具栏实现) ](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>请参阅

[状态栏](../mfc/status-bars.md)
