---
description: 了解有关以下方面的详细信息：服务器：实现服务器
title: 服务器：实现服务器
ms.date: 11/04/2016
helpviewer_keywords:
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
ms.openlocfilehash: 3ced10f88ce062ab571841610ba4b000571835b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217375"
---
# <a name="servers-implementing-a-server"></a>服务器：实现服务器

本文介绍 MFC 应用程序向导为视觉编辑服务器应用程序创建的代码。 如果不使用应用程序向导，本文会列出必须编写代码以实现服务器应用程序的区域。

如果使用应用程序向导创建新的服务器应用程序，它将为您提供大量的服务器特定代码。 如果要将视觉对象编辑服务器功能添加到现有应用程序，则必须复制应用程序向导在添加其余必需服务器代码之前提供的代码。

应用程序向导提供的服务器代码分为几个类别：

- 定义服务器资源：

  - 服务器在其自己的窗口中编辑嵌入项时使用的菜单资源。

  - 服务器处于活动状态时使用的菜单和工具栏资源。

  有关这些资源的详细信息，请参阅 [菜单和资源：服务器添加](../mfc/menus-and-resources-server-additions.md)。

- 定义派生自的项类 `COleServerItem` 。 有关服务器项的更多详细信息，请参阅 [服务器：服务器项](../mfc/servers-server-items.md)。

- 将 document 类的基类更改为 `COleServerDoc` 。 有关更多详细信息，请参阅 [服务器：实现服务器文档](../mfc/servers-implementing-server-documents.md)。

- 定义派生自的框架窗口类 `COleIPFrameWnd` 。 有关更多详细信息，请参阅 [服务器：实现 In-Place 框架窗口](../mfc/servers-implementing-in-place-frame-windows.md)。

- 在 Windows 注册数据库中为服务器应用程序创建一个条目，并使用 OLE 系统注册该服务器的新实例。 有关此主题的信息，请参阅 [注册](../mfc/registration.md)。

- 初始化并启动服务器应用程序。 有关此主题的信息，请参阅 [注册](../mfc/registration.md)。

有关详细信息，请参阅类库 *参考* 中的 [COleServerItem](../mfc/reference/coleserveritem-class.md)、 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)和 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) 。

## <a name="see-also"></a>请参阅

[服务器](../mfc/servers.md)<br/>
[容器](../mfc/containers.md)<br/>
[OLE)  (菜单和资源 ](../mfc/menus-and-resources-ole.md)<br/>
[注册](../mfc/registration.md)
