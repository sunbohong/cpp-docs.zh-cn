---
description: 详细了解：剪贴板：何时使用每个剪贴板机制
title: 剪贴板：何时使用每一剪贴板机制
ms.date: 11/04/2016
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard, guidelines
- Clipboard [MFC], mechanisms
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
- Clipboard [MFC], formats
ms.assetid: fd071996-ef8c-488b-81bd-89057095a201
ms.openlocfilehash: e2fae9fd2af38a9b39c488ec17adf1433edc098c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338405"
---
# <a name="clipboard-when-to-use-each-clipboard-mechanism"></a>剪贴板：何时使用每一剪贴板机制

使用剪贴板时，请遵循以下准则：

- 现在使用 OLE 剪贴板机制实现新功能。 虽然将保留标准剪贴板 API，但 OLE 机制是数据传输的未来。

- 如果要编写 OLE 应用程序或需要任何 OLE 功能，如拖放，请使用 OLE 剪贴板机制。

- 如果提供 OLE 格式，则使用 OLE 剪贴板机制。

## <a name="what-do-you-want-to-do"></a>要执行的操作

- [使用 OLE 剪贴板机制](clipboard-using-the-ole-clipboard-mechanism.md)

- [使用 Windows 剪贴板机制](clipboard-using-the-windows-clipboard.md)

## <a name="see-also"></a>请参阅

[剪贴板](clipboard.md)
