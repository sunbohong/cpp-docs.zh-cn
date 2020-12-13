---
description: 了解有关以下内容的详细信息： MFC 应用程序向导创建的文档和视图类
title: MFC 应用程序向导创建的文档和视图类
ms.date: 11/04/2016
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
ms.openlocfilehash: f182278ebdd971364e3e35e15e51b6ea5e7aaf68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330310"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>MFC 应用程序向导创建的文档和视图类

MFC 应用程序向导为您创建了主干文档和视图类，从而让您在程序开发中抢占先机。 然后，可以将 [命令和消息映射到这些类](reference/mapping-messages-to-functions.md) ，并使用 Visual C++ 源代码编辑器来编写其成员函数。

MFC 应用程序向导创建的文档类派生自类 [CDocument](reference/cdocument-class.md)。 视图类从 [CView](reference/cview-class.md)派生。 应用程序向导为这些类提供的名称以及包含这些类的文件基于您在“应用程序向导”对话框中提供的项目名称。 在应用程序向导中，您可以使用“生成的类”页修改默认名称。

某些应用程序可能需要多个文档类、视图类或框架窗口类。 有关详细信息，请参阅 [多文档类型、视图和框架窗口](multiple-document-types-views-and-frame-windows.md)。

## <a name="see-also"></a>请参阅

[文档/视图体系结构](document-view-architecture.md)
