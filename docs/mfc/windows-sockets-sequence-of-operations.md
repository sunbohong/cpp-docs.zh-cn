---
description: 了解更多相关信息： Windows 套接字：操作顺序
title: Windows 套接字：操作顺序
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
ms.openlocfilehash: 89870de642abcc8e0584c2c5dc93860eda9785e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263369"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows 套接字：操作顺序

本文介绍并行，一系列服务器套接字和客户端套接字的操作。 因为套接字使用 `CArchive` 对象，所以它们必须是 [流套接字](../mfc/windows-sockets-stream-sockets.md)。

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>流套接字通信的操作顺序

与构造 `CSocketFile` 对象的过程一样，以下顺序是准确的 (，但对于和) 有一些参数差异 `CAsyncSocket` `CSocket` 。 从该点开始，该序列严格适用于 `CSocket` 。 下表说明了用于设置客户端与服务器之间的通信的操作序列。

### <a name="setting-up-communication-between-a-server-and-a-client"></a>设置服务器和客户端之间的通信

|服务器|Client|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -或-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> -或//|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -或-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> -或//|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -或-<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -或-<br /><br /> `arOut << dwValue;`6|

1. 其中 *nPort* 是一个端口号。 有关端口的详细信息，请参阅 [Windows 套接字：端口和套接字地址](../mfc/windows-sockets-ports-and-socket-addresses.md) 。

2. 服务器必须始终指定一个端口，以便客户端可以连接。 `Create`调用有时还会指定一个地址。 在客户端上，使用默认参数，这些参数要求 MFC 使用任何可用的端口。

3. 其中， *nPort* 是一个端口号， *STRADDR* 是 (IP) 地址的计算机地址或 Internet 协议。

4. 计算机地址可以采用多种形式： "ftp.microsoft.com" 和 "microsoft.com"。 IP 地址使用 "点数" 形式的 "127.54.67.32"。 `Connect`函数会检查地址是否为点分数字 (虽然它不会进行检查以确保该数字是网络) 上的有效计算机。 如果不是，则 `Connect` 采用其他形式之一的计算机名。

5. 在 `Accept` 服务器端调用时，会将引用传递给新的套接字对象。 必须先构造此对象，但不要 `Create` 为其调用。 请记住，如果此套接字对象超出范围，则连接将关闭。 MFC 将新对象连接到 **套接字句** 柄。 可以在堆栈上构造套接字，如图所示，或在堆上构造。

6. 存档和套接字文件在超出范围时将关闭。 当对象超出范围或被删除时，套接对象的析构函数也会调用 socket 对象的 [Close](../mfc/reference/casyncsocket-class.md#close) 成员函数。

## <a name="additional-notes-about-the-sequence"></a>有关序列的其他说明

上表中所示的调用序列适用于流套接字。 数据报套接字（无连接）不需要 [CAsyncSocket：： Connect](../mfc/reference/casyncsocket-class.md#connect)、 [侦听](../mfc/reference/casyncsocket-class.md#listen)和 [Accept](../mfc/reference/casyncsocket-class.md#accept) 调用 (虽然您可以选择使用 `Connect`) 。 相反，如果使用的是类 `CAsyncSocket` ，数据报套接字使用 `CAsyncSocket::SendTo` 和 `ReceiveFrom` 成员函数。  (如果 `Connect` 与数据报套接字一起使用，请使用 `Send` 和 `Receive` 。 ) 因为 `CArchive` 无法与数据报一起使用，所以 `CSocket` 如果套接字是数据报，则不要将与存档一起使用。

[CSocketFile](../mfc/reference/csocketfile-class.md) 不支持所有的 `CFile` 功能; `CFile` 成员（如）不 `Seek` 能用于套接字通信。 因此，某些默认 MFC `Serialize` 函数与不兼容 `CSocketFile` 。 这对于类尤其如此 `CEditView` 。 不应尝试 `CEditView` 使用附加到对象的对象对数据进行序列化; 请改用 `CArchive` `CSocketFile` `CEditView::SerializeRaw` `CEditView::Serialize` (未记录) 。 [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw)函数要求文件对象具有不支持的函数，例如 `Seek` `CSocketFile` 。

有关详细信息，请参阅：

- [Windows 套接字：对存档使用套接字](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 套接字：使用类 CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 套接字：端口和套接字地址](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows 套接字：流套接字](../mfc/windows-sockets-stream-sockets.md)

- [Windows 套接字：数据报套接字](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket 类](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket：： Close](../mfc/reference/casyncsocket-class.md#close)
