---
description: 了解详细信息：典型 Internet 客户端应用程序中的步骤
title: 典型 Internet 客户端应用程序中的步骤
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
ms.openlocfilehash: 9660687136361efb0256ecdd1fd19b577c46ab26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216543"
---
# <a name="steps-in-a-typical-internet-client-application"></a>典型 Internet 客户端应用程序中的步骤

下表显示了你可以在典型的 Internet 客户端应用程序中执行的步骤。

|您的目标|采取的操作|效果|
|---------------|----------------------|-------------|
|开始 Internet 会话。|创建 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|初始化 WinInet 并连接到服务器。|
|设置 Internet 查询选项 (超时限制或重试次数，例如) 。|使用 [CInternetSession：： SetOption](../mfc/reference/cinternetsession-class.md#setoption)。|如果操作不成功，则返回 FALSE。|
|建立回调函数以监视会话的状态。|使用 [CInternetSession：： EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)。|为 [CInternetSession：： OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)建立回调。 重写 `OnStatusCallback` 以创建自己的回调例程。|
|连接到 Internet 服务器、intranet 服务器或本地文件。|使用 [CInternetSession：： OpenURL](../mfc/reference/cinternetsession-class.md#openurl)。|分析 URL 并打开到指定服务器的连接。 如果将本地文件名传递) ，则返回 [CStdioFile](../mfc/reference/cstdiofile-class.md) (`OpenURL` 。 这是通过其访问从服务器或文件检索到的数据的对象。|
|从文件中读取。|使用 [CInternetFile：： Read](../mfc/reference/cinternetfile-class.md#read)。|使用你提供的缓冲区读取指定的字节数。|
|处理异常。|使用 [CInternetException](../mfc/reference/cinternetexception-class.md) 类。|处理所有常见的 Internet 异常类型。|
|结束 Internet 会话。|释放 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|自动清理打开的文件句柄和连接。|

## <a name="see-also"></a>请参阅

[ (WinInet) 的 Win32 Internet 扩展 ](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet 客户端类的先决条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[使用 MFC WinInet 类编写 Internet 客户端应用程序](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
