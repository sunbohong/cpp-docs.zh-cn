---
description: 了解详细信息：典型 HTTP 客户端应用程序中的步骤
title: 典型 HTTP 客户端应用程序中的步骤
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: 0f08ca7629c389df67b579b8c20acceeb16b0cd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216595"
---
# <a name="steps-in-a-typical-http-client-application"></a>典型 HTTP 客户端应用程序中的步骤

下表显示了你可以在典型 HTTP 客户端应用程序中执行的步骤：

|您的目标|采取的操作|效果|
|---------------|----------------------|-------------|
|开始 HTTP 会话。|创建 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|初始化 WinInet 并连接到服务器。|
|连接到 HTTP 服务器。|使用 [CInternetSession：： GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)。|返回 [CHttpConnection](../mfc/reference/chttpconnection-class.md) 对象。|
|打开 HTTP 请求。|使用 [CHttpConnection：： OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest)。|返回 [CHttpFile](../mfc/reference/chttpfile-class.md) 对象。|
|发送 HTTP 请求。|使用 [CHttpFile：： AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) 和 [CHttpFile：： SendRequest](../mfc/reference/chttpfile-class.md#sendrequest)。|查找文件。 如果未找到文件，则返回 FALSE。|
|从文件中读取。|请使用 [CHttpFile](../mfc/reference/chttpfile-class.md)。|使用你提供的缓冲区读取指定的字节数。|
|处理异常。|使用 [CInternetException](../mfc/reference/cinternetexception-class.md) 类。|处理所有常见的 Internet 异常类型。|
|结束 HTTP 会话。|释放 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|自动清理打开的文件句柄和连接。|

## <a name="see-also"></a>请参阅

[ (WinInet) 的 Win32 Internet 扩展 ](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet 客户端类的先决条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[使用 MFC WinInet 类编写 Internet 客户端应用程序](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
