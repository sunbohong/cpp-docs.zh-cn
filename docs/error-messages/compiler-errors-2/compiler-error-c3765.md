---
title: 编译器错误 C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 5bb2dba57c680882bb4bf8e4026f5720276b47b4
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509371"
---
# <a name="compiler-error-c3765"></a>编译器错误 C3765

"event"：不能在标记为 event_receiver 的类/结构 "type" 中定义事件

如果用 [event_receiver](../../windows/attributes/event-receiver.md) 特性标记了类，则该类不能包含 [__event](../../cpp/event.md) 声明。

下面的示例生成 C3765：

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
