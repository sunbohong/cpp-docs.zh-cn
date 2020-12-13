---
description: 了解有关以下内容的详细信息： Windows 套接字：从套接字类派生
title: Windows 套接字：从套接字类派生
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
ms.openlocfilehash: ba3526ddde4d254ff044fa09588d7764b16fb719
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132959"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows 套接字：从套接字类派生

本文介绍通过从一个套接字类派生你自己的类可以获得的一些功能。

可以从 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 或 [CSocket](../mfc/reference/csocket-class.md) 派生自己的套接字类，以添加自己的功能。 特别是，这些类提供了许多可以重写的虚拟成员函数。 这些函数包括 [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)、 [OnSend](../mfc/reference/casyncsocket-class.md#onsend)、 [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept)、 [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect)和 [OnClose](../mfc/reference/casyncsocket-class.md#onclose)。 您可以重写派生套接类中的函数，以利用它们在网络事件发生时所提供的通知。 框架调用这些通知回调函数来通知您重要的套接字事件，例如接收可以开始读取的数据。 有关通知函数的详细信息，请参阅 [Windows 套接字：套接字通知](../mfc/windows-sockets-socket-notifications.md)。

此外，类还 `CSocket` 提供了 [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) 成员函数 (高级可重写) 。 MFC 在发送基于 Windows 的消息时调用此函数。 您可以通过重写 `OnMessagePending` 来查找 Windows 中的特定消息并对其进行响应。

`OnMessagePending`类中提供的默认版本在 `CSocket` 等待阻塞调用完成时检查消息队列中是否有 WM_PAINT 消息。 它调度绘制消息以提高显示质量。 除了执行一些有用的操作，这说明了您可以自己重写函数的一种方法。 作为另一个示例，请考虑使用 `OnMessagePending` 执行以下任务。 假设您在等待网络事务完成时显示无模式对话框。 该对话框包含一个 "取消" 按钮，用户可以使用该按钮取消阻止时间太长的事务。 `OnMessagePending`重写可能会抽取与此无模式对话框相关的消息。

在 `OnMessagePending` 重写中，返回 **TRUE** 或从对的基类版本的调用返回 `OnMessagePending` 。 如果执行你仍想要完成的工作，请调用基类版本。

有关详细信息，请参阅：

- [Windows 套接字：对存档使用套接字](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 套接字：使用类 CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 套接字：锁定](../mfc/windows-sockets-blocking.md)

- [Windows 套接字：字节排序](../mfc/windows-sockets-byte-ordering.md)

- [Windows 套接字：转换字符串](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)
