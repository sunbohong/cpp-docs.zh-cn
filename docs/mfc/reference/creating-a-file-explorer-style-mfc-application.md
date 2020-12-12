---
description: 了解详细信息： Explorer-Style MFC 应用程序创建文件
title: 创建文件资源管理器样式的 MFC 应用程序
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcexplorer.project
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
ms.openlocfilehash: 9419aae58cf34ec70585b952360cb12702424381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301316"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>创建文件资源管理器样式的 MFC 应用程序

许多 Windows 系统应用程序使用用户界面 (UI) 用于文件资源管理器。 例如，当你启动文件资源管理器时，你会看到一个应用程序，该应用程序具有划分工作区的垂直拆分条。 工作区左侧提供导航和浏览功能，而工作区右侧显示与左窗格中的选择相关的详细信息。 当用户单击左窗格中的某个项时，应用程序将重新填充右窗格。 在 MDI 应用程序中，可以使用 " **视图** " 菜单上的命令来更改右窗格中显示的详细信息量。  (在 SDI 或多个顶级文档应用程序中，只能使用工具栏按钮来更改详细信息。 ) 

窗格的内容取决于应用程序。 在文件系统浏览器中，左窗格显示目录或计算机或计算机组的分层视图，而右窗格显示文件夹、单个文件或计算机，以及有关它们的详细信息。 内容不一定必须是文件。 它们可能是电子邮件、错误报告或数据库中的其他项目。

向导将为你创建以下类：

- `CLeftView`类定义工作区的左窗格。 它始终从 [CTreeView](../../mfc/reference/ctreeview-class.md)派生。

- C *ProjName* View 类定义工作区的右窗格。 默认情况下，它派生自 [CListView](../../mfc/reference/clistview-class.md) ，但可以是另一种类型的视图，具体取决于在向导的 "生成的 [类](../../mfc/reference/generated-classes-mfc-application-wizard.md)" 页的 "**基类**" 列表中指定的类。

生成的应用程序可以具有单文档界面 (SDI) 、多文档界面 (MDI) 或多个顶级文档结构。 应用程序创建的每个框架窗口均使用 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)进行垂直拆分。 编码此应用程序类型与编写使用拆分器的普通 MFC 应用程序类似，只是这种类型的应用程序在每个拆分器窗格中都有单独的控制视图。

如果在右窗格中使用默认列表视图，则向导将在 MDI 应用程序中 (创建其他菜单选项，这些选项仅) 和工具栏按钮，用于在大图标、小图标、列表和详细信息模式之间切换视图的样式。

### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>开始创建文件资源管理器样式的 MFC 可执行文件

1. 按照 [创建 MFC 应用程序](../../mfc/reference/creating-an-mfc-application.md)中的说明进行操作。

1. 在 "MFC 应用程序向导 [应用程序类型](../../mfc/reference/application-type-mfc-application-wizard.md) " 页上，选择 " **文件资源管理器** " 项目样式。

1. 在向导的其他页面上设置所需的任何其他选项。

1. 单击 " **完成** " 生成主干应用程序。

有关详细信息，请参阅：

- [多文档类型、视图和框架窗口](../../mfc/multiple-document-types-views-and-frame-windows.md)

- [派生视图类](../../mfc/derived-view-classes-available-in-mfc.md)

- [应用程序设计选择](../../mfc/application-design-choices.md)

## <a name="see-also"></a>请参阅

[MFC 应用程序向导](../../mfc/reference/mfc-application-wizard.md)<br/>
[创建 Web Browser-Style MFC 应用程序](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)<br/>
[创建 Forms-Based MFC 应用程序](../../mfc/reference/creating-a-forms-based-mfc-application.md)
