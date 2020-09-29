---
title: 添加 ATL 对话框
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
ms.openlocfilehash: 71290cf0763ac6594985acc4cb11562efe7028e6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499364"
---
# <a name="adding-an-atl-dialog-box"></a>添加 ATL 对话框

若要向项目中添加 ATL 对话框，你的项目必须是 ATL 项目或包含 ATL 支持的 MFC 项目。 您可以使用 [Atl 项目向导](../../atl/reference/atl-project-wizard.md) 创建 atl 应用程序，或 [将 atl 对象添加到 mfc 应用](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) 程序，以便为 MFC 应用程序实现 atl 支持。

默认情况下，ATL 对话框向导实现从 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)派生的对话框。 此类包括对承载 ActiveX 和 Windows 控件的支持。 如果你不希望获得 ActiveX 控件支持的开销，则在向导生成代码后，请将的所有实例替换 `CAxDialogImpl` 为 [CSimpleDialog](../../atl/reference/csimpledialog-class.md) 或 [CDialogImpl](../../atl/reference/cdialogimpl-class.md) 作为基类。

> [!NOTE]
> `CSimpleDialog` 仅创建支持 Windows 公共控件的模式对话框。 `CDialogImpl` 创建模式对话框或无模式对话框。

## <a name="to-add-an-atl-dialog-resource-to-your-project"></a>向项目添加 ATL 对话框资源

1. 使用 [Atl 项目向导](../../atl/reference/atl-project-wizard.md)创建 ATL 项目。

1. 在 [类视图](/visualstudio/ide/viewing-the-structure-of-code)中，右键单击项目名称，然后从快捷菜单中单击 " **添加** "。 单击“添加类”****。

1. 在 "[添加类](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box)" 对话框的 "**模板**" 窗格中，单击 " **ATL 对话框**"。 单击 " **打开** " 显示 [ATL 对话框向导](../../atl/reference/atl-dialog-wizard.md)。

有关详细信息，请参阅 [实现对话框](../../atl/implementing-a-dialog-box.md)。

## <a name="see-also"></a>请参阅

[添加类](../../ide/adding-a-class-visual-cpp.md)<br/>
[窗口类](../../atl/atl-window-classes.md)<br/>
[消息映射](../../atl/message-maps-atl.md)
