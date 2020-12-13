---
description: 了解详细信息：分配和取消分配窗口内存
title: 分配和取消分配窗口内存
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: 7648914289babffdfb5195f1ec53cd736e26892c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343713"
---
# <a name="allocating-and-deallocating-window-memory"></a>分配和取消分配窗口内存

不要使用 c + + **`delete`** 运算符销毁框架窗口或视图。 请改为调用 `CWnd` 成员函数 `DestroyWindow` 。 因此，应在带有运算符的堆上分配框架窗口 **`new`** 。 在堆栈帧上或全局分配框架窗口时请小心。 应尽可能在堆栈帧上分配其他窗口。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [创建窗口](creating-windows.md)

- [窗口销毁序列](window-destruction-sequence.md)

- [将 CWnd 从 HWND 中分离出来](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>请参阅

[销毁窗口对象](destroying-window-objects.md)
