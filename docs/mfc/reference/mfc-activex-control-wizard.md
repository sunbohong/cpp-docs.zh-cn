---
description: 了解更多： MFC ActiveX 控件向导
title: MFC ActiveX 控件向导
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: f313f2a218c06a20eddbfff33e936109e4be2cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219260"
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX 控件向导

ActiveX 控件是特定类型的 [自动化服务器](../../mfc/automation-servers.md);它是一个可重用的组件。 承载 ActiveX 控件的应用程序是该控件的 [自动化客户端](../../mfc/automation-clients.md) 。 如果你的目标是创建这种可重用的组件，请使用此向导来创建控件。 有关详细信息，请参阅 [MFC ActiveX 控件](../../mfc/mfc-activex-controls.md) 。

>[!IMPORTANT]
> ActiveX 是一种不能用于新开发的旧技术。 有关取代 ActiveX 的新式技术的详细信息，请参阅 [Activex 控件](../activex-controls.md)。

或者，您可以使用 [Mfc 应用程序向导](../../mfc/reference/mfc-application-wizard.md)创建自动化服务器 MFC 应用程序。

使用此向导创建的 ActiveX 控件可以有一个用户界面，也可以不可见。 您可以在向导的 " [控件设置](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) " 页中指定此选项。 计时器控件是您希望不可见的 ActiveX 控件的一个示例。

ActiveX 控件可以具有复杂的用户界面。 某些控件可能类似于封装的窗体：包含多个字段的单个控件，每个字段本身都是一个 Windows 控件。 例如，作为 MFC ActiveX 控件实现的自动部件对象可能会显示类似窗体的用户界面，用户可以通过该界面读取和编辑部件号、部件名称和其他信息。 有关详细信息，请参阅 [MFC ActiveX 控件](../../mfc/mfc-activex-controls.md) 。

如果需要为 ActiveX 对象创建容器，请参阅 [创建 Activex 控件容器](../../mfc/reference/creating-an-mfc-activex-control-container.md)。

MFC starter 程序包含 c + + 源 ( .cpp) 文件、资源 ( .rc) 文件和项目 () 文件。 这些初学者文件中生成的代码基于 MFC。

下面的示例列表显示了 ActiveX 控件的任务和类型的增强功能：

- [优化 ActiveX 控件](../../mfc/mfc-activex-controls-optimization.md)

- [向 ActiveX 控件添加常用事件](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [添加自定义事件](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [添加常用方法](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [添加自定义方法](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [添加常用属性](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [添加自定义属性](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [对 ActiveX 控件容器中的 ActiveX 控件编程](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>概述

此向导页描述你正在创建的 MFC ActiveX 控件项目的当前应用程序设置。 默认情况下，该向导创建一个项目，如下所示：

- 默认项目不生成运行时许可证或帮助文件。 您可以在 " [应用程序设置](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) " 页上更改这些默认设置。 " **概述** " 页上只会反映在 ActiveX 控件向导的此页上所做的选择。

- 该项目包含一个控件类和一个属性页类，该项目的名称基于项目的名称。 您可以在 " [控件名称](../../mfc/reference/control-names-mfc-activex-control-wizard.md) " 页上编辑项目的名称和文件名。

- 控件基于无现有的 Windows 控件，在可见时激活，具有用户界面，并包括 " **关于** " 对话框。 您可以在 " [控件设置](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) " 页上更改这些默认设置。

## <a name="see-also"></a>请参阅

[Visual Studio 项目 - C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual Studio 中的 C++ 项目类型](../../build/reference/visual-cpp-project-types.md)<br/>
[概念](../../atl/active-template-library-atl-concepts.md)
