---
description: 了解详细信息：避免堆争用
title: 避免堆争用
ms.date: 11/04/2016
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
ms.openlocfilehash: c58849bee46dd0d870d1067f17581429339fbc0e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142566"
---
# <a name="avoidance-of-heap-contention"></a>避免堆争用

MFC 和 ATL 提供的默认字符串管理器是在全局堆之上的简单包装器。 此全局堆完全是线程安全的，这意味着多个线程可以同时分配内存和释放内存，而不会损坏堆。 为了帮助提供线程安全，堆必须将访问序列化到自身。 通常使用关键部分或类似的锁定机制来完成此操作。 当两个线程尝试同时访问堆时，一个线程会被阻止，直到另一个线程的请求完成。 对于许多应用程序而言，这种情况很少发生，堆锁定机制对性能的影响也不能忽略。 但是，如果应用程序经常从多个线程中访问堆，则堆锁的争用会导致应用程序运行速度慢于单线程 (，即使是在具有多个 Cpu 的计算机上) 。

使用 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 的应用程序特别容易遭受堆争用，因为对 `CStringT` 对象的操作经常需要重新分配字符串缓冲区。

缓解线程间的堆争用的一种方法是让每个线程都从专用的线程本地堆中分配字符串。 只要使用特定线程的分配器分配的字符串只在该线程中使用，则分配器不需要是线程安全的。

## <a name="example"></a>示例

下面的示例演示了一个线程过程，该过程将分配其自己的专用非线程安全堆以用于该线程上的字符串：

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>注释

使用此同一个线程过程可以运行多个线程，但由于每个线程都有自己的堆，因此线程之间没有争用。 此外，如果每个堆不是线程安全的，即使只有一个线程的副本正在运行，也可以显著提高性能。 这是因为堆不使用昂贵的联锁操作来防范并发访问。

对于更复杂的线程过程，可以方便地在线程本地存储中将指向线程的字符串管理器的指针存储 (TLS) 槽。 这允许线程过程调用的其他函数访问线程的字符串管理器。

## <a name="see-also"></a>请参阅

[内存管理与 CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
