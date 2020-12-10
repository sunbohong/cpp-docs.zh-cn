---
title: Microsoft 基础类 (MFC) 应用程序体系结构类
description: Microsoft 基础类 (MFC) 库应用程序体系结构类的概述。
ms.date: 12/08/2020
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.openlocfilehash: 65aa9707d361c6d014c67c0f9ff1af86e19087de
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933191"
---
# <a name="mfc-application-architecture-classes"></a>MFC 应用程序体系结构类

此类别中 (MFC) 类的 Microsoft 基础类库有助于 MFC 应用程序的体系结构。 它们提供大部分应用程序常见的功能。 填充框架以添加应用程序特定功能。 通常，您通过从体系结构类派生新的类，然后添加新成员或重写现有成员函数来实现。

[应用程序向导](reference/mfc-application-wizard.md) 生成多种类型的应用程序，所有这些应用程序都以不同的方式使用应用程序框架。 SDI (单文档界面) 和 MDI (多文档界面) 应用程序可充分利用框架的文档/视图部分。 其他类型的应用程序（如基于对话框的应用程序、基于窗体的应用程序和 DLL）仅使用部分文档/视图体系结构功能。

文档/视图应用程序包含一个或多个文档、视图和框架窗口集。 文档模板对象将每个文档/视图/框架集的类关联起来。

您无需在 MFC 应用程序中使用文档/视图体系结构，但这样做有很多好处。 MFC OLE 容器和服务器支持基于文档/视图体系结构，如对打印和打印预览的支持。

所有 MFC 应用程序至少有两个对象：派生自的应用程序对象 [`CWinApp`](reference/cwinapp-class.md) ，以及某些类型的主窗口对象，派生 (通常间接) [`CWnd`](reference/cwnd-class.md) 。  (最常见的情况是，主窗口派生自 [`CFrameWnd`](reference/cframewnd-class.md) 、 [`CMDIFrameWnd`](reference/cmdiframewnd-class.md) 或 [`CDialog`](reference/cdialog-class.md) ，所有这些都是从派生的 `CWnd` 。 ) 

使用文档/视图体系结构的应用程序包含其他对象。 主要对象包括：

- 如前面所述，从类派生的应用程序对象 [`CWinApp`](reference/cwinapp-class.md) 。
- 从类派生的一个或多个文档类对象 [`CDocument`](reference/cdocument-class.md) 。 文档类对象负责在视图中操作的数据的内部表示形式。 它们可能与数据文件关联。
- 从类派生的一个或多个视图对象 [`CView`](reference/cview-class.md) 。 每个视图都是附加到文档并与框架窗口关联的一个窗口。 视图显示和操作文档类对象中包含的数据。

文档/视图应用程序还包含从 [`CFrameWnd`](reference/cframewnd-class.md)) 派生的) 和文档 (模板派生的框架窗口 ([`CDocTemplate`](reference/cdoctemplate-class.md) 。

## <a name="see-also"></a>另请参阅

[类概述](class-library-overview.md)