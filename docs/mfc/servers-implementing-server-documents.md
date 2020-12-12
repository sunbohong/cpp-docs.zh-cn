---
description: 了解有关以下方面的详细信息：服务器：实现服务器文档
title: 服务器：实现服务器文档
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
ms.openlocfilehash: b8843d3e2ac662cbb018a3063c9f04f5dd8d6f10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217323"
---
# <a name="servers-implementing-server-documents"></a>服务器：实现服务器文档

本文介绍了在应用程序向导中未指定 "OLE 服务器" 选项的情况下，成功实现服务器文档所必须执行的步骤。

#### <a name="to-define-a-server-document-class"></a>定义服务器文档类

1. 从 `COleServerDoc` 而不是 `CDocument` 派生您的文档类。

1. 创建从派生的服务器项类 `COleServerItem` 。

1. 实现 `OnGetEmbeddedItem` 服务器文档类的成员函数。

   `OnGetEmbeddedItem` 当容器应用程序的用户创建或编辑嵌入项时，将调用。 它应返回表示整个文档的项。 这应该是派生类的对象 `COleServerItem` 。

1. 重写 `Serialize` 成员函数以序列化文档的内容。 不需要序列化服务器项的列表，除非您使用它们来表示文档中的本机数据。 有关详细信息，请参阅 [Servers： Server items](../mfc/servers-server-items.md)中的 "*实现服务器项*"。

当创建服务器文档时，框架会自动向 OLE 系统 Dll 注册文档。 这允许 Dll 标识服务器文档。

有关详细信息，请参阅类库 *参考* 中的 [COleServerItem](../mfc/reference/coleserveritem-class.md)和 [COleServerDoc](../mfc/reference/coleserverdoc-class.md) 。

## <a name="see-also"></a>请参阅

[服务器](../mfc/servers.md)<br/>
[服务器：服务器项](../mfc/servers-server-items.md)<br/>
[服务器：实现服务器](../mfc/servers-implementing-a-server.md)<br/>
[服务器：实现 In-Place 框架窗口](../mfc/servers-implementing-in-place-frame-windows.md)
