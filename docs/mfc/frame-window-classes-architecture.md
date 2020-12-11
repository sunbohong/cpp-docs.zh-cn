---
description: '了解详细信息：框架窗口类 (体系结构) '
title: 框架窗口类（体系结构）
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: 045108cd1e45325cf6069b5d8259ffab9abb0c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155028"
---
# <a name="frame-window-classes-architecture"></a>框架窗口类（体系结构）

在文档/视图体系结构中，框架窗口是包含 "视图" 窗口的窗口。 它们还支持附加控件条。

在多文档界面中 (MDI) 应用程序，主窗口派生自 `CMDIFrameWnd` 。 它间接包含文档的框架，即 `CMDIChildWnd` 对象。 `CMDIChildWnd`对象反过来也包含文档的视图。

在单文档界面中 (SDI) 应用程序（从派生的主窗口） `CFrameWnd` 包含当前文档的视图。

[CFrameWnd](reference/cframewnd-class.md)<br/>
SDI 应用程序的主框架窗口的基类。 也是其他所有框架窗口类的基类。

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI 应用程序的主框架窗口的基类。

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI 应用程序的文档框架窗口的基类。

[COleIPFrameWnd](reference/coleipframewnd-class.md)<br/>
当正在就地编辑服务器文档时，提供视图的框架窗口。

## <a name="see-also"></a>请参阅

[类概述](class-library-overview.md)
