---
description: 了解更多：编译器错误 C3765
title: 编译器错误 C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 29de872030143ab33e1349f07ac3b81cb841e113
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234613"
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
