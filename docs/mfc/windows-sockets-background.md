---
description: 了解更多相关信息： Windows 套接字：背景
title: Windows 套接字：背景
ms.date: 11/04/2016
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
ms.openlocfilehash: 9ac373f5f81dfe3914664d14122a7a6bd46cda40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214463"
---
# <a name="windows-sockets-background"></a>Windows 套接字：背景

本文介绍 Windows 套接字的性质和用途。 本文还介绍了以下内容：

- [定义 "socket" 一词](#_core_definition_of_a_socket)。

- [介绍套接字句数据类型](#_core_the_socket_data_type)。

- [介绍套接字的用法](#_core_uses_for_sockets)。

Windows 套接字规范为 Microsoft Windows 定义了二进制兼容的网络编程接口。 Windows 套接字基于 Berkeley 软件分发中的 UNIX 套接字实现 (BSD，版本 4.3) 来自加利福尼亚大学的 Berkeley。 该规范包含 BSD 特定于 Windows 的类型化套接字例程和扩展。 使用 Windows 套接字可允许应用程序在符合 Windows 套接字 API 的任何网络之间进行通信。 在 Win32 上，Windows 套接字提供线程安全。

许多网络软件供应商支持网络协议下的 Windows 套接字，包括传输控制协议/Internet 协议 (TCP/IP) 、Xerox 网络系统 (XNS) 、数字设备公司的 DECNet 协议、Novell 公司的 Internet 数据包交换/有序打包 Exchange (IPX/SPX) 等。 尽管当前的 Windows 套接字规范定义了 TCP/IP 的套接字抽象，但任何网络协议都可以通过提供其自己的动态链接库版本 (DLL) 来实现 Windows 套接字，从而符合 Windows 套接字。 Windows 套接字编写的商业应用程序示例包括： X Windows 服务器、终端模拟器和电子邮件系统。

> [!NOTE]
> Windows 套接字的用途是抽象掉底层网络，这样您就不必熟悉该网络，因此您的应用程序可以在支持套接字的任何网络上运行。 因此，本文档不讨论网络协议的详细信息。

MFC) Microsoft 基础类库 (支持通过提供两个类来使用 Windows 套接字 API 进行编程。 其中一类提供了 `CSocket` 高级别的抽象，以简化网络通信编程。

Windows 套接规范，Windows 套接字： Microsoft Windows 中的网络计算的开放接口现在是版本1.1，它是 TCP/IP 社区中的大量个人和公司的开放网络标准，可自由使用。 套接字编程模型目前支持使用 Internet 协议套件的一个 "通信域"。 Windows SDK 中提供了该规范。

> [!TIP]
> 由于套接字使用 Internet 协议套件，因此它们是在 "信息高速公路" 上支持 Internet 通信的应用程序的首选路由。

## <a name="definition-of-a-socket"></a><a name="_core_definition_of_a_socket"></a> 套接字的定义

套接字是一个通信终结点，它是一个对象，Windows 套接字应用程序通过它在网络中发送或接收数据包。 套接字具有类型并且与正在运行的进程相关联，并且它可能具有一个名称。 目前，套接字通常仅与使用 Internet 协议套件的同一 "通信域" 中的其他套接字交换数据。

这两种套接字都是双向的;它们是可在两个方向上同时 (全双工) 的数据流。

有两种套接字类型可用：

- 流套接字

   流套接字提供没有记录边界的数据流：字节流。 保证流的传递和顺序正确，并无重复。

- 数据报套接字

   数据报套接字支持面向记录的数据流，该数据流不保证被传递，也不能被序列化为已发送或无重复。

"有序" 表示按发送的顺序传送数据包。 "无重复" 表示只获取一次特定数据包。

> [!NOTE]
> 在某些网络协议（如 XNS）下，流可以面向记录，而不是以字节流的形式进行记录。 但在更常见的 TCP/IP 协议下，流是字节流。 Windows 套接字提供独立于基础协议的抽象级别。

有关这些类型以及在哪些情况下使用哪种类型的套接字的信息，请参阅 [Windows 套接字：流套接字](../mfc/windows-sockets-stream-sockets.md) 和 [Windows 套接字：数据报套接字](../mfc/windows-sockets-datagram-sockets.md)。

## <a name="the-socket-data-type"></a><a name="_core_the_socket_data_type"></a> 套接字数据类型

每个 MFC 套接字对象封装 Windows 套接对象的句柄。 此句柄的数据类型为 **SOCKET**。 **套接字** 句柄类似于 `HWND` 窗口的。 MFC 套接字类提供封装句柄上的操作。

**套接字** 数据类型在 Windows SDK 中有详细描述。 请参阅 Windows 套接字下的 "套接字数据类型和错误值"。

## <a name="uses-for-sockets"></a><a name="_core_uses_for_sockets"></a> 用于套接字

套接字在至少三个通信上下文中非常有用：

- 客户端/服务器模型。

- 对等方案，如消息传递应用程序。

- 通过使接收应用程序将消息解释为函数调用，使远程过程调用 (RPC) 。

> [!TIP]
> 使用 MFC 套接字的理想情况是在同时编写通信的两端：在两端使用 MFC。 有关此主题的详细信息（包括如何在与非 MFC 应用程序通信时管理案例），请参阅 [Windows 套接字：字节排序](../mfc/windows-sockets-byte-ordering.md)。

有关详细信息，请参阅 Windows 套接字规范： **ntohs**、 **ntohl**、 **htons**、 **htonl**。 另请参阅以下主题：

- [Windows 套接字：对存档使用套接字](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 套接字：使用存档的套接字示例](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows 套接字：使用类 CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)
