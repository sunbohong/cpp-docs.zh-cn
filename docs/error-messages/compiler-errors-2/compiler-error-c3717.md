---
description: 了解更多：编译器错误 C3717
title: 编译器错误 C3717
ms.date: 11/04/2016
f1_keywords:
- C3717
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
ms.openlocfilehash: fecd417af1eceb40ef8b8e48fda40b3ec5e5b36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189426"
---
# <a name="compiler-error-c3717"></a>编译器错误 C3717

"method"：不能定义激发事件的方法

你声明了一个包含实现的事件方法。 [__Event](../../cpp/event.md)方法声明不能有定义。 若要修复此错误，请确保没有事件方法声明具有定义。 例如，在下面的代码中，从声明中删除注释所指示的函数体 `event1` 。

下面的示例生成 C3717：

```cpp
// C3717.cpp
[event_source(native)]
class CEventSrc {
public:
   __event void event1() {   // C3717
   }

   // remove definition for event1 and substitute following declaration
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {
   }

   void HookEvents(CEventSrc* pSrc) {
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};

int main() {
}
```
