---
description: 了解详细信息： Win32 Internet 类
title: Win32 Internet 类
ms.date: 09/12/2018
f1_keywords:
- vc.classes.win32
helpviewer_keywords:
- Internet classes [MFC]
- WinInet classes [MFC], classes
- Win32 [MFC], Internet classes
- Windows API [MFC], Internet classes
ms.assetid: b49601d5-3025-4068-9408-316b54ee4375
ms.openlocfilehash: 8b6acad5f867444c33ed86cb7e70f4f1eec42df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197473"
---
# <a name="win32-internet-classes"></a>Win32 Internet 类

MFC 将 Win32 Internet 封装 (WinInet) 和 ActiveX 技术，使 Internet 编程更容易。

>[!IMPORTANT]
> ActiveX 是一种不能用于新开发的旧技术。 有关取代 ActiveX 的新式技术的详细信息，请参阅 [Activex 控件](activex-controls.md)。

[CInternetSession](../mfc/reference/cinternetsession-class.md)<br/>
创建并初始化一个 Internet 会话或多个同时 Internet 会话，并在必要时描述与代理服务器的连接。

[CInternetConnection](../mfc/reference/cinternetconnection-class.md)<br/>
管理与 Internet 服务器的连接。

[CInternetFile](../mfc/reference/cinternetfile-class.md)<br/>
此类及其派生类允许访问使用 Internet 协议的远程系统上的文件。

[CHttpConnection](../mfc/reference/chttpconnection-class.md)<br/>
管理与 HTTP 服务器的连接。

[CHttpFile](../mfc/reference/chttpfile-class.md)<br/>
提供查找和读取 HTTP 服务器上文件的功能。

[CGopherFile](../mfc/reference/cgopherfile-class.md)<br/>
提供查找和读取 Gopher 服务器上文件的功能。

[CFtpConnection](../mfc/reference/cftpconnection-class.md)<br/>
管理与 FTP 服务器的连接。

[CGopherConnection](../mfc/reference/cgopherconnection-class.md)<br/>
管理与 gopher 服务器的连接。

[CFileFind](../mfc/reference/cfilefind-class.md)<br/>
执行本地和 Internet 文件搜索。

[CFtpFileFind](../mfc/reference/cftpfilefind-class.md)<br/>
辅助 FTP 服务器的 Internet 文件搜索。

[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)<br/>
辅助 Gopher 服务器的 Internet 文件搜索。

[CGopherLocator](../mfc/reference/cgopherlocator-class.md)<br/>
从 Gopher 服务器获取 Gopher“定位器”，确定定位器的类型，并使定位器可用于 `CGopherFileFind`。

[CInternetException](../mfc/reference/cinternetexception-class.md)<br/>
表示与 Internet 操作相关的异常条件。

## <a name="see-also"></a>请参阅

[类概述](../mfc/class-library-overview.md)
