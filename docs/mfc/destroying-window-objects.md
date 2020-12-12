---
description: 了解更多：销毁窗口对象
title: 销毁窗口对象
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: c2837ba6b9f568d7f6ab0175ae3ad99c31ccdc7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327816"
---
# <a name="destroying-window-objects"></a>销毁窗口对象

当用户完成窗口时，必须注意您自己的子窗口以销毁 c + + 窗口对象。 如果未销毁这些对象，您的应用程序将不会恢复其内存。 幸运的是，该框架管理窗口销毁以及框架窗口、视图和对话框的创建。 如果创建其他窗口，您将负责销毁它们。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [窗口销毁序列](window-destruction-sequence.md)

- [分配和取消分配窗口内存](allocating-and-deallocating-window-memory.md)

- [将 CWnd 从 HWND 中分离出来](detaching-a-cwnd-from-its-hwnd.md)

- [常规窗口创建顺序](general-window-creation-sequence.md)

- [销毁框架窗口](destroying-frame-windows.md)

## <a name="see-also"></a>请参阅

[窗口对象](window-objects.md)
