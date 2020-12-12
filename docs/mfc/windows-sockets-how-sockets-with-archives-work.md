---
description: 了解有关以下内容的详细信息： Windows 套接字：包含存档的套接字如何工作
title: Windows 套接字：使用存档的套接字如何工作
ms.date: 11/19/2018
helpviewer_keywords:
- Windows Sockets [MFC], synchronous
- sockets [MFC], synchronous operation
- sockets [MFC], with archives
- synchronous state socket
- Windows Sockets [MFC], with archives
- two-state socket object
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
ms.openlocfilehash: 19b24a9942b7405304c9037091266b4535bffbc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263538"
---
# <a name="windows-sockets-how-sockets-with-archives-work"></a>Windows 套接字：使用存档的套接字如何工作

本文介绍如何结合使用 [CSocket](../mfc/reference/csocket-class.md) 对象、 [CSocketFile](../mfc/reference/csocketfile-class.md) 对象和 [CArchive](../mfc/reference/carchive-class.md) 对象，以简化通过 Windows 套接字发送和接收数据的操作。

[Windows 套接字：使用存档的套接字的示例](../mfc/windows-sockets-example-of-sockets-using-archives.md)显示了 `PacketSerialize` 函数。 示例中的 archive 对象 `PacketSerialize` 非常类似于传递到 MFC [序列化](../mfc/reference/cobject-class.md#serialize) 函数的存档对象。 关键区别在于，对于套接字，存档附加到标准的 [CFile](../mfc/reference/cfile-class.md) 对象， (通常与) 的磁盘文件相关联，而不是与对象相关联 `CSocketFile` 。 对象连接到对象，而不是连接到磁盘文件 `CSocketFile` `CSocket` 。

`CArchive`对象管理缓冲区。 当存储 (发送) 存档的缓冲区已满时，关联 `CFile` 对象写出缓冲区的内容。 刷新附加到套接字的存档缓冲区等效于发送消息。 当) 存档的加载 (的缓冲区已满时，对象将 `CFile` 停止读取，直到缓冲区再次可用。

类 `CSocketFile` 派生自 `CFile` ，但它不支持 [CFile](../mfc/reference/cfile-class.md) 成员函数，例如 (、、等的定位函数 `Seek` `GetLength` `SetLength`) 、 (`LockRange` 、 `UnlockRange`) 或函数的锁定函数 `GetPosition` 。 所有 [CSocketFile](../mfc/reference/csocketfile-class.md) 对象都必须与关联的对象有写入或读取的字节序列 `CSocket` 。 由于不涉及文件，因此等操作 `Seek` 并 `GetPosition` 不合理。 `CSocketFile` 派生自 `CFile` ，因此它通常会继承所有这些成员函数。 为避免出现这种 `CFile` 情况，在中重写不受支持的成员函数， `CSocketFile` 以引发 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)。

`CSocketFile`对象调用其对象的成员函数 `CSocket` 来发送或接收数据。

下图显示了通信两端的这些对象之间的关系。

![CArchive、CSocketFile 和 CSocket](../mfc/media/vc38ia1.gif "CArchive、CSocketFile 和 CSocket") <br/>
CArchive、CSocketFile 和 CSocket

这种明显的复杂性是为了使您不需要自行管理套接字的详细信息。 创建套接字、文件和存档，然后开始发送或接收数据，方法是将其插入存档或从存档中提取数据。 [CArchive](../mfc/reference/carchive-class.md)、 [CSocketFile](../mfc/reference/csocketfile-class.md)和 [CSocket](../mfc/reference/csocket-class.md) 管理幕后的详细信息。

`CSocket`对象实际上是两状态对象：异步 (通常状态) ，有时是同步的。 在其异步状态下，套接字可以从框架接收异步通知。 但是，在执行操作（如接收或发送数据）期间，套接字将同步。 这意味着在同步操作完成之前，套接字将不再收到异步通知。 由于它切换模式，因此，您可以执行类似于下面的操作：

[!code-cpp[NVC_MFCSimpleSocket#2](../mfc/codesnippet/cpp/windows-sockets-how-sockets-with-archives-work_1.cpp)]

如果 `CSocket` 未实现为两状态对象，则在处理以前的通知时，可能会收到针对相同事件类型的其他通知。 例如，你可能会在 `OnReceive` 处理时收到通知 `OnReceive` 。 在上述代码片段中， `str` 从存档中提取可能会导致递归。 通过切换状态， `CSocket` 可以防止其他通知阻止递归。 一般规则是通知内没有通知。

> [!NOTE]
> `CSocketFile`还可用作不带对象的 (受限) 文件 `CArchive` 。 默认情况下， `CSocketFile` 构造函数的 *bArchiveCompatible* 参数为 **TRUE**。 这会指定文件对象用于存档。 若要在不使用存档的情况下使用 file 对象，请在 *bArchiveCompatible* 参数中传递 **FALSE** 。

对象在其 "存档兼容" 模式下 `CSocketFile` 提供更好的性能，并降低 "死锁" 的风险。 当发送和接收套接字彼此等待，或等待公共资源时，会发生死锁。 如果 `CArchive` 对象与对象的处理方式相同，则可能会发生这种情况 `CSocketFile` `CFile` 。 对于 `CFile` ，存档可以假定，如果它接收的字节数少于所请求的字节数，则已到达文件结尾。 `CSocketFile`但对于，数据是基于消息的; 缓冲区可包含多条消息，因此，接收的字节数少于所请求的字节数，而不表示文件尾。 在这种情况下，应用程序不会被阻止，这种情况下 `CFile` ，它可以继续从缓冲区读取消息，直到缓冲区为空。 在这种情况下，中的 [IsBufferEmpty](../mfc/reference/carchive-class.md#isbufferempty) 函数 `CArchive` 对于监视存档缓冲区的状态很有用。

有关详细信息，请参阅 [Windows 套接字：对存档使用套接字](../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)<br/>
[CObject：：串行化](../mfc/reference/cobject-class.md#serialize)
