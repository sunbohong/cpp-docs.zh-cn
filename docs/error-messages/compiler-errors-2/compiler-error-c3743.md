---
description: 了解更多：编译器错误 C3743
title: 编译器错误 C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: 1afad204f25220df53d58313a5742424e3491710
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340237"
---
# <a name="compiler-error-c3743"></a>编译器错误 C3743

当 event_receiver 的 "layout_dependent" 参数为 true 时，只能挂钩/解除挂钩整个接口

[__Unhook](../../cpp/unhook.md)函数根据传递给 `layout_dependent` [event_receiver](../../windows/attributes/event-receiver.md)类中的参数的值，它所采用的参数数量不同。

下面的示例生成 C3743：

```cpp
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```
