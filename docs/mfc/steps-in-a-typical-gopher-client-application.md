---
description: 了解详细信息：典型 Gopher 客户端应用程序中的步骤
title: 典型 Gopher 客户端应用程序中的步骤
ms.date: 11/04/2016
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
ms.openlocfilehash: 23940457acf52009b6d334deec129324a53a7583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216621"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>典型 Gopher 客户端应用程序中的步骤

下表显示了你可以在典型 gopher 客户端应用程序中执行的步骤。

|您的目标|采取的操作|效果|
|---------------|----------------------|-------------|
|开始 gopher 会话。|创建 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|初始化 WinInet 并连接到服务器。|
|连接到 gopher 服务器。|使用 [CInternetSession：： GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection)。|返回 [CGopherConnection](../mfc/reference/cgopherconnection-class.md) 对象。|
|查找 gopher 中的第一个资源。|使用 [CGopherFileFind：： FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)。|查找第一个文件。 如果未找到文件，则返回 FALSE。|
|查找 gopher 中的下一个资源。|使用 [CGopherFileFind：： FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile)。|查找下一个文件。 如果未找到文件，则返回 FALSE。|
|打开或打开的文件 `FindFile` `FindNextFile` 以进行读取。|使用 [CGopherFileFind：： GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator)获取 gopher 定位符。 使用 [CGopherConnection：： OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)。|打开定位符指定的文件。 `OpenFile` 返回 [CGopherFile](../mfc/reference/cgopherfile-class.md) 对象。|
|使用提供的 gopher 定位符打开文件。|使用 [CGopherConnection：： CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)创建 gopher 定位符。 使用 [CGopherConnection：： OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)。|打开定位符指定的文件。 `OpenFile` 返回 [CGopherFile](../mfc/reference/cgopherfile-class.md) 对象。|
|从文件中读取。|请使用 [CGopherFile](../mfc/reference/cgopherfile-class.md)。|使用您提供的缓冲区读取指定的字节数。|
|处理异常。|使用 [CInternetException](../mfc/reference/cinternetexception-class.md) 类。|处理所有常见的 Internet 异常类型。|
|结束 gopher 会话。|释放 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|自动清理打开的文件句柄和连接。|

## <a name="see-also"></a>请参阅

[ (WinInet) 的 Win32 Internet 扩展 ](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet 客户端类的先决条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[使用 MFC WinInet 类编写 Internet 客户端应用程序](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
