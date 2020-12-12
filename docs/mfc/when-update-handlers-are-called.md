---
description: 了解详细信息：调用更新处理程序时
title: 何时调用更新处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: ee5d402eea4121c9ceb4bcbd48e752549c55b1c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297169"
---
# <a name="when-update-handlers-are-called"></a>何时调用更新处理程序

假设用户在 "File" （文件）菜单中单击鼠标，这将生成 WM_INITMENUPOPUP 消息。 在菜单下拉以便用户可看到它之前，框架的更新机制将统一更新“文件”菜单中的所有项。

为此，在标准命令路由过程中，框架路由将更新弹出菜单中所有菜单项的命令。 路由上的命令目标有机会更新任何菜单项，方式为将更新命令与适当的消息映射项（属于 `ON_UPDATE_COMMAND_UI` 窗体）匹配并调用“更新处理程序”函数。 因此，对于包含六个菜单项的菜单，将发出六个 update 命令。如果菜单项的命令 ID 存在更新处理程序，则将调用该处理程序来执行更新。 如果不存在，则框架将检查是否存在此命令 ID 的处理程序并启用或禁用菜单项（根据需要）。

如果框架在命令路由期间未找到 `ON_UPDATE_COMMAND_UI` 项，则在某个位置存在具有相同命令 ID 的 `ON_COMMAND` 项时，框架将自动启用用户界面对象。 否则，它将禁用用户界面对象。 因此，若要确保启用用户界面对象，请为对象生成的命令提供一个处理程序或为之提供一个更新处理程序。 请参阅主题 [用户界面对象和命令 id](../mfc/user-interface-objects-and-command-ids.md)中的图。

可禁用用户界面对象的默认禁用。 有关详细信息，请参阅 [](../mfc/reference/cframewnd-class.md#m_bautomenuenable) `CFrameWnd` *MFC 参考* 中类的 m_bAutoMenuEnable 成员。

菜单初始化是在框架中自动进行的，在应用程序收到 WM_INITMENUPOPUP 消息时出现。 在空闲循环期间，框架将通过其为菜单执行的同一方式为按钮更新处理程序搜索命令路由。

## <a name="see-also"></a>请参阅

[如何：更新 User-Interface 对象](../mfc/how-to-update-user-interface-objects.md)
