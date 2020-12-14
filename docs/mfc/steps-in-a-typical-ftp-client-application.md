---
description: 了解详细信息：典型 FTP 客户端应用程序中的步骤
title: 典型 FTP 客户端应用程序中的步骤
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
ms.openlocfilehash: caac613adf3ad886c4b36ae567a3b8c5c928ee10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216634"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>典型 FTP 客户端应用程序中的步骤

典型的 FTP 客户端应用程序创建一个 [CInternetSession](../mfc/reference/cinternetsession-class.md) 和一个 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 对象。 请注意，这些 MFC WinInet 类并不实际控制代理类型设置;IIS 的功能。

下表显示了你可以在典型 FTP 客户端应用程序中执行的步骤。

|您的目标|采取的操作|效果|
|---------------|----------------------|-------------|
|FTP 会话开始。|创建 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|初始化 WinInet 并连接到服务器。|
|连接到 FTP 服务器。|使用 [CInternetSession：： GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)。|返回 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 对象。|
|更改为服务器上的新 FTP 目录。|使用 [CFtpConnection：： SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)。|更改服务器上当前连接到的目录。|
|查找 FTP 目录中的第一个文件。|使用 [CFtpFileFind：： FindFile](../mfc/reference/cftpfilefind-class.md#findfile)。|查找第一个文件。 如果未找到文件，则返回 FALSE。|
|查找 FTP 目录中的下一个文件。|使用 [CFtpFileFind：： FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)。|查找下一个文件。 如果未找到文件，则返回 FALSE。|
|打开或打开的文件 `FindFile` `FindNextFile` 以进行读取或写入。|使用 [CFtpConnection：： OpenFile](../mfc/reference/cftpconnection-class.md#openfile)，并使用 [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) 或 [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)返回的文件名。|打开服务器上的文件以进行读取或写入。 返回 [CInternetFile](../mfc/reference/cinternetfile-class.md) 对象。|
|读取或写入文件。|使用 [CInternetFile：： Read](../mfc/reference/cinternetfile-class.md#read) 或 [CInternetFile：： Write](../mfc/reference/cinternetfile-class.md#write)。|使用您提供的缓冲区读取或写入指定的字节数。|
|处理异常。|使用 [CInternetException](../mfc/reference/cinternetexception-class.md) 类。|处理所有常见的 Internet 异常类型。|
|结束 FTP 会话。|释放 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|自动清理打开的文件句柄和连接。|

## <a name="see-also"></a>请参阅

[ (WinInet) 的 Win32 Internet 扩展 ](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet 客户端类的先决条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[使用 MFC WinInet 类编写 Internet 客户端应用程序](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
