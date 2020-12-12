---
description: 了解更多相关信息：用户定义的工具
title: 用户定义的工具
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 4cccd0a68751a2f196c8c2e652088e8939e3f162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263629"
---
# <a name="user-defined-tools"></a>用户定义的工具

MFC 支持用户定义的工具。 用户定义工具是一种特殊的命令，可执行外部用户指定的程序。 您可以使用自定义过程来管理用户定义的工具。 但是，如果您的应用程序对象不是从 [CWinAppEx 类](../mfc/reference/cwinappex-class.md)派生的，则不能使用此进程。 有关自定义的详细信息，请参阅 [MFC 自定义](../mfc/customization-for-mfc.md)。

如果启用了用户定义的工具支持，"自定义" 对话框将自动包含 " **工具** " 选项卡。下图显示了 " **工具** " 页。

![“自定义”对话框中的“工具”选项卡](../mfc/media/custdialogboxtoolstab.png "“自定义”对话框中的“工具”选项卡") <br/>
自定义对话框 "工具" 选项卡

## <a name="enabling-user-defined-tools-support"></a>启用用户定义的工具支持

若要在应用程序中启用用户定义的工具，请调用 [CWinAppEx：： EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)。 但是，必须先在应用程序的资源文件中定义多个常量，以用作此调用的参数。

在资源编辑器中，创建一个使用适当的命令 ID 的虚拟命令。 在下面的示例中，我们使用 `ID_TOOLS_ENTRY` 作为命令 ID。 此命令 ID 在一个或多个菜单中标记一个位置，框架将在其中插入用户定义的工具。

必须在字符串表中保留一些连续的 Id，以表示用户定义的工具。 留出的字符串数等于用户可以定义的最大用户工具数。 在下面的示例中，这些名称 `ID_USER_TOOL1` 通过命名 `ID_USER_TOOL10` 。

你可以为用户提供建议，以帮助他们选择将作为工具调用的外部程序的目录和参数。 为此，请在 "资源编辑器" 中创建两个弹出菜单。 在下面的示例中，这些命名为 `IDR_MENU_ARGS` 和 `IDR_MENU_DIRS` 。 对于这些菜单中的每个命令，请在应用程序字符串表中定义一个字符串。 字符串的资源 ID 必须等于命令 ID。

还可以从 [CUserTool 类](../mfc/reference/cusertool-class.md) 创建派生类来替换默认实现。 为此，请将派生类的运行时信息作为第四个参数传递给 CWinAppEx：： EnableUserTools，而不是 RUNTIME_CLASS ([CUserTool 类](../mfc/reference/cusertool-class.md)) 。

定义适当的常量后，调用 [CWinAppEx：： EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) 以启用用户定义的工具。

下面的方法调用显示了如何使用这些常量：

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

在此示例中，"工具" 选项卡将包括在 " **自定义** " 对话框中。 `ID_TOOLS_ENTRY`每当用户打开该菜单时，框架会将任何与当前定义的用户工具集匹配的任何菜单中的命令 ID 替换为任意命令。 命令 Id `ID_USER_TOOL1` 通过 `ID_USER_TOOL10` 保留以用于用户定义的工具。 类 [CUserTool 类](../mfc/reference/cusertool-class.md) 处理对用户工具的调用。 " **自定义** " 对话框的 "工具" 选项卡提供了参数和目录输入字段右侧的按钮，用于访问 **IDR_MENU_ARGS** 和 **IDR_MENU_DIRS** 的菜单。当用户从这些菜单中选择一个命令时，框架会将其资源 ID 等于命令 ID 的字符串追加到相应的文本框。

### <a name="including-predefined-tools"></a>包括预定义的工具

如果要在应用程序启动时预定义某些工具，则必须重写应用程序主窗口的 [CFrameWnd：： LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 方法。 在该方法中，必须执行以下步骤。

##### <a name="to-add-new-tools-in-loadframe"></a>在 LoadFrame 中添加新工具

1. 通过调用[CWinAppEx：： GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager)获取指向[CUserToolsManager 类](../mfc/reference/cusertoolsmanager-class.md)对象的指针。

1. 对于要创建的每个工具，请调用 [CUserToolsManager：： CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)。 此方法返回指向 [CUserTool 类](../mfc/reference/cusertool-class.md) 对象的指针，并将新创建的用户工具添加到工具的内部集合。 如果向[CWinAppEx：： EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)的第四个参数提供了[CUserTool 类](../mfc/reference/cusertool-class.md)的派生类的运行时信息， [CUserToolsManager：： CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)将实例化并返回该类的实例。

1. 对于每个工具，通过设置来设置其文本标签， `CUserTool::m_strLabel` 并通过调用设置其命令 `CUserTool::SetCommand` 。 [CUserTool 类](../mfc/reference/cusertool-class.md)的默认实现会自动从对的调用中指定的程序中检索可用图标 `SetCommand` 。

## <a name="see-also"></a>请参阅

[MFC 自定义](../mfc/customization-for-mfc.md)<br/>
[CUserTool 类](../mfc/reference/cusertool-class.md)<br/>
[CUserToolsManager 类](../mfc/reference/cusertoolsmanager-class.md)<br/>
[CWinAppEx 类](../mfc/reference/cwinappex-class.md)
