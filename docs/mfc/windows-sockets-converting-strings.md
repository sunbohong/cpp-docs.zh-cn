---
description: 了解更多相关信息： Windows 套接字：转换字符串
title: Windows 套接字：转换字符串
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: fe8607647192fadc7f0d5d32d7716c222ff9206f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118623"
---
# <a name="windows-sockets-converting-strings"></a>Windows 套接字：转换字符串

本文和两篇配套文章介绍了 Windows 套接字编程中的若干问题。 本文介绍如何转换字符串。 [Windows 套接字：阻止](../mfc/windows-sockets-blocking.md)和[windows 套接字：字节排序](../mfc/windows-sockets-byte-ordering.md)中介绍了其他问题。

如果使用类 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)或从类派生，则需自行管理这些问题。 如果使用类 [CSocket](../mfc/reference/csocket-class.md)或从类派生，则 MFC 会为你进行管理。

## <a name="converting-strings"></a>转换字符串

如果在使用以不同宽字符格式存储的字符串的应用程序之间进行通信（如 Unicode 或多字节字符集 (MBCS) ，或在其中一个和使用 ANSI 字符串的应用程序之间进行通信，则必须在下管理转换 `CAsyncSocket` 。 `CArchive`与对象一起使用的对象 `CSocket` 通过类[CString](../atl-mfc-shared/reference/cstringt-class.md)的功能管理此转换。 有关详细信息，请参阅位于 Windows SDK 中的 Windows 套接字规范。

有关详细信息，请参阅：

- [Windows 套接字：使用类 CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 套接字：对存档使用套接字](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 套接字：背景](../mfc/windows-sockets-background.md)

- [Windows 套接字：流套接字](../mfc/windows-sockets-stream-sockets.md)

- [Windows 套接字：数据报套接字](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>请参阅

[MFC 中的 Windows 套接字](../mfc/windows-sockets-in-mfc.md)
