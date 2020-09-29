---
title: 编译器错误 C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: 7235d86ed00663b81aaddb87fdeae957c0f73053
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500422"
---
# <a name="compiler-error-c3739"></a>编译器错误 C3739

"class"：只有当 event_receiver 的 "layout_dependent" 参数为 true 时，才支持语法

尝试挂钩整个事件接口，但 `layout_dependent` 在 [event_receiver](../../windows/attributes/event-receiver.md) 属性为 true 时，必须一次挂钩一个事件。

下面的示例生成 C3739：

```cpp
// C3739.cpp
struct A
{
   __event void e();
};

// event_receiver is implied
// [ event_receiver(layout_dependent=false)]

// use the following line instead
// [event_receiver(com, layout_dependent=true), coclass ]
struct B
{
   void f();
   B(A* a)
   {
      __hook(A, a, &B::f);   // C3739
      // use the following line instead to hook a single event
      // __hook(&A::e, a, &B::f);
   }
};

int main()
{
}
```
