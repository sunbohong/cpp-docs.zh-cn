---
description: 了解详细信息：在典型 FTP 客户端应用程序中删除文件的步骤
title: 在典型 FTP 客户端应用程序中用于删除文件的步骤
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 0de5ba71ac127a44c964571d243997bcb49faaa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216647"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>在典型 FTP 客户端应用程序中用于删除文件的步骤

下表显示了在典型的删除文件的 FTP 客户端应用程序中可能执行的步骤。

|您的目标|采取的操作|效果|
|---------------|----------------------|-------------|
|FTP 会话开始。|创建 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|初始化 WinInet 并连接到服务器。|
|连接到 FTP 服务器。|使用 [CInternetSession：： GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)。|返回 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 对象。|
|检查以确保处于 FTP 服务器上的正确目录中。|使用 [CFtpConnection：： GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) 或 [CFtpConnection：： GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl)。|根据选择的成员函数，返回服务器上当前连接到的目录的名称或 URL。|
|更改为服务器上的新 FTP 目录。|使用 [CFtpConnection：： SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)。|更改服务器上当前连接到的目录。|
|查找 FTP 目录中的第一个文件。|使用 [CFtpFileFind：： FindFile](../mfc/reference/cftpfilefind-class.md#findfile)。|查找第一个文件。 如果未找到文件，则返回 FALSE。|
|查找 FTP 目录中的下一个文件。|使用 [CFtpFileFind：： FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)。|查找下一个文件。 如果未找到文件，则返回 FALSE。|
|删除由或找到的 `FindFile` 文件 `FindNextFile` 。|使用 [CFtpConnection：： Remove](../mfc/reference/cftpconnection-class.md#remove)，并使用由或返回的 `FindFile` 文件名 `FindNextFile` 。|删除服务器上用于读取或写入的文件。|
|处理异常。|使用 [CInternetException](../mfc/reference/cinternetexception-class.md) 类。|处理所有常见的 Internet 异常类型。|
|结束 FTP 会话。|释放 [CInternetSession](../mfc/reference/cinternetsession-class.md) 对象。|自动清理打开的文件句柄和连接。|

## <a name="see-also"></a>请参阅

[ (WinInet) 的 Win32 Internet 扩展 ](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet 客户端类的先决条件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[使用 MFC WinInet 类编写 Internet 客户端应用程序](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
