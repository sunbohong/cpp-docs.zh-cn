---
description: 了解更多相关信息： Windows 套接字：端口和套接字地址
title: Windows 套接字：端口和套接字地址
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: 354505796ff60cc8968b2e10a2aac98be2eb4666
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263395"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows 套接字：端口和套接字地址

本文介绍了与 Windows 套接字一起使用的术语 "端口" 和 "地址"。

## <a name="port"></a><a name="_core_port"></a> 口

端口标识可为其提供服务的唯一进程。 在当前上下文中，端口与支持 Windows 套接字的应用程序相关联。 其思路是唯一标识每个 Windows 套接字应用程序，以便可以在一台计算机上同时运行多个 Windows 套接字应用程序。

某些端口是为常见服务（如 FTP）保留的。 你应避免使用这些端口，除非提供此类服务。 Windows 套接字规范详细说明了这些保留端口。 文件 WINSOCK。H 还会列出它们。

若要让 Windows 套接 DLL 为你选择可用端口，请将0作为端口值传递。 MFC 选择一个大于 1024 decimal 的端口值。 可以通过调用 [CAsyncSocket：： GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) 成员函数来检索 MFC 选择的端口值。

## <a name="socket-address"></a><a name="_core_socket_address"></a> 套接字地址

每个套接字对象均与网络上 (IP) 地址的 Internet 协议关联。 通常，地址是计算机名称，如 "ftp.microsoft.com" 或点分数字，如 "128.56.22.8"。

当你尝试创建套接字时，通常无需指定你自己的地址。

> [!NOTE]
> 您的计算机可能 (多个网卡，或者您的应用程序可能会在) 的计算机上运行，每个计算机代表一个不同的网络。 如果是这样，您可能需要指定一个地址来指定套接字将使用哪个网卡。 这是一种高级用法和可能的可移植性问题。

有关详细信息，请参阅：

- [Windows 套接字：使用类 CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 套接字：对存档使用套接字](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 套接字：使用存档的套接字如何工作](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 套接字：流套接字](../mfc/windows-sockets-stream-sockets.md)

- [Windows 套接字：数据报套接字](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)
