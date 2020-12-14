---
description: 了解更多： MFC 应用程序向导
title: MFC 应用程序向导
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 645f0e1ed3f1f35c109d524a8c63fa36231bc61a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219208"
---
# <a name="mfc-application-wizard"></a>MFC 应用程序向导

MFC 应用程序向导将生成一个应用程序，在编译该应用程序时，它将实现 Windows 可执行文件 () 应用程序的基本功能。 MFC 入门应用程序包含 c + + 源 ( .cpp) 文件、资源 ( .rc) 文件、头 () 文件和项目 () 文件。 这些初学者文件中生成的代码基于 MFC。

> [!NOTE]
> 根据你选择的选项，向导会在你的项目中创建其他文件。 例如，如果您在 "[高级功能](../../mfc/reference/advanced-features-mfc-application-wizard.md)" 页上选择了 **上下文相关的帮助**，则向导将创建编译项目的帮助文件所必需的文件。 有关向导创建的文件的详细信息，请参阅 [为 Visual Studio c + + 项目创建的文件类型](../../build/reference/file-types-created-for-visual-cpp-projects.md)，然后查看项目中的 Readme.txt 文件。

## <a name="overview"></a>概述

此向导页描述你正在创建的 MFC 应用程序的当前应用程序设置。 默认情况下，该向导创建一个项目，如下所示：

- [MFC 应用程序向导的应用程序类型](../../mfc/reference/application-type-mfc-application-wizard.md)

  - 项目是通过选项卡式多文档界面 (MDI) 支持创建的。 有关详细信息，请参阅 [SDI 和 MDI](../../mfc/sdi-and-mdi.md)。

  - 该项目使用 [文档/视图体系结构](../../mfc/document-view-architecture.md)。

  - 该项目使用 Unicode 库。

  - 使用 Visual Studio 项目样式创建项目，并启用视觉样式切换。

  - 项目在共享 DLL 中使用 MFC。 有关详细信息，请参阅 [在 Visual Studio 中创建 c/c + + dll](../../build/dlls-in-visual-cpp.md)。

- [MFC 应用程序向导的复合文档支持](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

  - 该项目不支持复合文档。

- [MFC 应用程序向导的文档模板字符串](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

  - 项目使用默认文档模板字符串的项目名称。

- [MFC 应用程序向导的数据库支持](../../mfc/reference/database-support-mfc-application-wizard.md)

  - 项目不提供对数据库的支持。

- [MFC 应用程序向导的用户界面功能](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

  - 该项目实现了标准的 Windows 用户界面功能，如系统菜单、状态栏、最大化和最小化框、" **关于** " 框、标准菜单栏和停靠工具栏以及子框架。

- [MFC 应用程序向导的高级功能](../../mfc/reference/advanced-features-mfc-application-wizard.md)

  - 项目支持打印和打印预览。

  - 项目支持 ActiveX 控件。 有关详细信息，请参阅 [用于创建 ActiveX 控件的操作顺序](../../mfc/sequence-of-operations-for-creating-activex-controls.md)。

  - 该项目不提供对 [自动化](../../mfc/automation.md)、 [MAPI](../../mfc/mapi-support-in-mfc.md)、 [Windows 套接字](../../mfc/windows-sockets-in-mfc.md)或 Active Accessibility 的支持。

  - 项目支持 " **资源管理器** 停靠" 窗格、" **输出** 停靠" 窗格和 " **属性** " 停靠窗格。

- [MFC 应用程序向导的生成的类](../../mfc/reference/generated-classes-mfc-application-wizard.md)

  - 项目的视图类派生自 [CView 类](../../mfc/reference/cview-class.md)。

  - 项目的应用程序类派生自 [CWinAppEx 类](../../mfc/reference/cwinappex-class.md)。

  - 项目的文档类派生自 [CDocument 类](../../mfc/reference/cdocument-class.md)。

  - 项目的主框架类派生自 [CMDIFrameWndEx 类](../../mfc/reference/cmdiframewndex-class.md)。

  - 项目的子框架类派生自 [CMDIChildWndEx 类](../../mfc/reference/cmdichildwndex-class.md)。

若要更改这些默认设置，请单击向导左列中的相应选项卡标题，并在显示的页上进行更改。

创建 MFC 应用程序项目后，可以使用 Visual C++ [代码向导](../../ide/adding-functionality-with-code-wizards-cpp.md)将对象或控件添加到项目。

## <a name="see-also"></a>请参阅

[创建 MFC 应用程序](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC 桌面应用程序](../../mfc/mfc-desktop-applications.md)<br/>
[使用类编写适用于 Windows 的应用程序](../../mfc/using-the-classes-to-write-applications-for-windows.md)
