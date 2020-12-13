---
description: 了解详细信息： Document-Template 类
title: 文档模板类
ms.date: 11/04/2016
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
ms.openlocfilehash: f9e67cc8f6a115345f6b1f42c2064fcbed7be47e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330273"
---
# <a name="document-template-classes"></a>文档模板类

创建新文档或视图时，文档模板对象协调文档、视图和框架窗口对象的创建。

[CDocTemplate](reference/cdoctemplate-class.md)<br/>
文档模板的基类。 永远不会直接使用此类;而是使用派生自此类的其他文档模板类之一。

[CMultiDocTemplate](reference/cmultidoctemplate-class.md)<br/>
多文档界面中文档的模板 (MDI) 。 MDI 应用程序一次可以打开多个文档。

[CSingleDocTemplate](reference/csingledoctemplate-class.md)<br/>
单文档界面中文档的模板 (SDI) 。 SDI 应用程序一次只能打开一个文档。

## <a name="related-class"></a>相关类

[CCreateContext](reference/ccreatecontext-structure.md)<br/>
文档模板传递给窗口创建函数的结构，用来协调文档、视图和框架窗口对象的创建。

## <a name="see-also"></a>请参阅

[类概述](class-library-overview.md)
