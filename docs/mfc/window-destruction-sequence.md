---
description: 了解详细信息：窗口析构序列
title: 窗口析构序列
ms.date: 11/04/2016
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
ms.openlocfilehash: 2ba60f1dcd3668a754bbe4384a6c8cf6b4d541d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207678"
---
# <a name="window-destruction-sequence"></a>窗口析构序列

在 MFC 框架中，当用户关闭框架窗口时，窗口的默认 [OnClose](../mfc/reference/cwnd-class.md#onclose) 处理程序将调用 [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)。 销毁 Windows 窗口时调用的最后一个成员函数是 [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)，它执行一些清理，调用 [默认](../mfc/reference/cwnd-class.md#default) 成员函数来执行 Windows 清理，最后调用虚拟成员函数 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)。 的 [CFrameWnd](../mfc/reference/cframewnd-class.md) 实现将 `PostNcDestroy` 删除 c + + 窗口对象。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [分配和取消分配窗口内存](../mfc/allocating-and-deallocating-window-memory.md)

- [将 CWnd 从 HWND 中分离出来](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>请参阅

[销毁窗口对象](../mfc/destroying-window-objects.md)
