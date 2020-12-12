---
description: 了解详细信息：使用类编写适用于 Windows 的应用程序
title: 使用类编写 Windows 应用程序
ms.date: 11/04/2016
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
ms.openlocfilehash: b94155b565872b614efa291699cecbaf4770fdaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322707"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>使用类编写 Windows 应用程序

同时，Microsoft 基础类 (MFC) 库中的类构成一个 "应用程序框架"，您可以在其中为 Windows 操作系统生成应用程序。 一般来说，框架定义了应用程序的主干，并提供可放置到主干上的标准用户界面实现。 作为编程人员，您的工作就是填写主干的其余部分，这是特定于您的应用程序的内容。 您可以通过使用 MFC 应用程序向导为非常详尽的入门应用程序创建文件来开始使用。 使用 Microsoft Visual C++ 资源编辑器可直观地设计用户界面元素，类视图用于将这些元素连接到代码的命令，以及用于实现应用程序特定逻辑的类库。

MFC framework 版本3.0 和更高版本支持 Win32 平台（包括 Microsoft Windows 95 和更高版本）和 Windows NT 版本3.51 及更高版本的编程。 MFC Win32 支持包括多线程处理。 如果需要进行16位编程，请使用版本 1.5 *x* 。

此系列文章提供了应用程序框架的广泛概述。 它还会探讨构成应用程序的主要对象及其创建方式。 这些文章涉及的主题包括：

- [框架](../mfc/framework-mfc.md)。

- 框架和代码之间的劳动划分，如在 [框架中生成](../mfc/building-on-the-framework.md)中所述。

- [应用程序类](../mfc/cwinapp-the-application-class.md)，用于封装应用程序级功能。

- [文档模板](../mfc/document-templates-and-the-document-view-creation-process.md)如何创建和管理文档及其关联的视图和框架窗口。

- [CWnd](../mfc/window-objects.md)类，所有窗口的根基类。

- [图形对象](../mfc/graphic-objects.md)，如笔和画笔。

框架的其他部分包括：

- [窗口对象：概述](../mfc/window-objects.md)

- [消息处理和映射](../mfc/message-handling-and-mapping.md)

- [CObject，MFC 中的根基类](../mfc/using-cobject.md)

- [文档/视图体系结构](../mfc/document-view-architecture.md)

- [对话框](../mfc/dialog-boxes.md)

- [控件](../mfc/controls-mfc.md)

- [控制条](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [内存管理](../mfc/memory-management.md)

   除了为 Windows 操作系统编写应用程序提供优点之外，MFC 还可以更轻松地编写专门使用 OLE 链接和嵌入技术的应用程序。 您可以使您的应用程序成为 OLE 可视化编辑容器和/或 OLE 可视编辑服务器，并且可以添加自动化，以便其他应用程序可以使用来自您的应用程序的对象，甚至可以通过远程方式驱动对象。

- [MFC ActiveX 控件](../mfc/mfc-activex-controls.md)

   OLE control 开发工具包 (CDK) 现已与框架完全集成。 本文系列提供 ActiveX 控件使用 MFC 进行开发的概述。  (ActiveX 控件以前称为 OLE 控件。 ) 

- [数据库编程](../data/data-access-programming-mfc-atl.md)

   MFC 还提供了两组数据库类，它们可简化数据访问应用程序的编写。 使用 ODBC 数据库类，可以通过开放式数据库连接 (ODBC) 驱动程序连接到数据库，从表中选择记录，并在屏幕表单中显示记录信息。 使用 (DAO) 类的数据访问对象，可以通过 Microsoft Jet 数据库引擎或外部 (非 Jet) 数据源（包括 ODBC 数据源）来处理数据库。

   此外，MFC 完全启用用于编写使用 Unicode 和多字节字符集 (MBCS) 的应用程序，特别是双字节字符集 (DBCS) 。

有关 MFC 文档的一般指南，请参阅 [常规 Mfc 主题](../mfc/general-mfc-topics.md)。

## <a name="see-also"></a>请参阅

[常规 MFC 主题](../mfc/general-mfc-topics.md)
