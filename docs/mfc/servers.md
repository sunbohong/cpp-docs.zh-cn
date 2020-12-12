---
description: 了解有关以下方面的详细信息：服务器
title: 服务器
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC]
- OLE server applications [MFC], activation
- full-server
- servers
- mini-server
- OLE server applications [MFC], server types
- server applications [MFC]
ms.assetid: e45172e8-eae3-400a-8139-0fa009a42fdc
ms.openlocfilehash: 5e9a9dd7cbb1ab237712b5ad0c84e3114a119ee3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217297"
---
# <a name="servers"></a>服务器

服务器应用程序 (或组件应用程序) 创建 OLE 项 (或组件) 供容器应用程序使用。 可视化编辑服务器应用程序还支持可视化编辑或就地激活。 OLE 服务器的另一种形式是 [自动化服务器](../mfc/automation-servers.md)。 某些服务器应用程序仅支持创建嵌入项;其他类支持创建嵌入项和链接项。 某些只支持链接，但这种情况很罕见。 当用户要编辑项时，所有服务器应用程序都必须支持容器应用程序激活。 应用程序可以同时为容器和服务器。 换句话说，它可以将数据合并到其文档中，并创建可作为项合并到其他应用程序的文档中的数据。

袖珍服务器是一种特殊类型的服务器应用程序，只能由容器启动。 Microsoft Draw 和 Microsoft Graph 是 miniservers 的示例。 袖珍不会将文档以文件的形式存储在磁盘上。 相反，它从读取其文档，并将其写入到容器所属文档中的项。 因此，袖珍只支持嵌入，而不支持链接。

完整服务器可以作为独立的应用程序运行，也可以由容器应用程序启动。 完整服务器可以将文档存储为磁盘上的文件。 它只能支持嵌入、嵌入和链接，或仅支持链接。 容器应用程序的用户可以通过选择服务器中的 "剪切" 或 "复制" 命令和容器中的 "粘贴" 命令来创建嵌入项。 通过选择服务器中的复制命令和容器中的 "粘贴链接" 命令来创建链接项。 或者，用户可以使用 "插入对象" 对话框创建嵌入项或链接项。

下表汇总了不同类型服务器的特征：

### <a name="server-characteristics"></a>服务器特征

|服务器类型|支持多个实例|每个文档的项|每个实例的文档数|
|--------------------|---------------------------------|------------------------|----------------------------|
|袖珍|是|1|1|
|SDI 完全服务器|是|1 (如果支持链接，则为1个或更多) |1|
|MDI full 服务器|无 (不需要) |1 (如果支持链接，则为1个或更多) |0 个或更多|

如果有多个容器用于编辑嵌入项或链接项，服务器应用程序应同时支持多个容器。 如果服务器是 SDI 应用程序 (或具有对话框界面) 的袖珍服务器，则服务器的多个实例必须能够同时运行。 这允许应用程序的单独实例处理每个容器请求。

如果服务器是一个 MDI 应用程序，则每次容器需要编辑项时，它都可以创建一个新的 MDI 子窗口。 通过这种方式，应用程序的单个实例可支持多个容器。

如果另一个容器请求服务器的一个实例已在运行，则服务器应用程序必须告知 OLE 系统 Dll 应执行的操作：是启动新的服务器实例，还是将所有容器的请求定向到服务器的一个实例。

有关服务器的详细信息，请参阅：

- [服务器：实现服务器](../mfc/servers-implementing-a-server.md)

- [服务器：实现服务器文档](../mfc/servers-implementing-server-documents.md)

- [服务器：实现 In-Place 框架窗口](../mfc/servers-implementing-in-place-frame-windows.md)

- [服务器：服务器项](../mfc/servers-server-items.md)

- [服务器： User-Interface 问题](../mfc/servers-user-interface-issues.md)

## <a name="see-also"></a>请参阅

[OLE](../mfc/ole-in-mfc.md)<br/>
[容器](../mfc/containers.md)<br/>
[容器：高级功能](../mfc/containers-advanced-features.md)<br/>
[OLE)  (菜单和资源 ](../mfc/menus-and-resources-ole.md)<br/>
[注册](../mfc/registration.md)<br/>
[自动化服务器](../mfc/automation-servers.md)
