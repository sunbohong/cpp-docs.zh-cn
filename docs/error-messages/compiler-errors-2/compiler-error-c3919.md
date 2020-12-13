---
description: 了解更多：编译器错误 C3919
title: 编译器错误 C3919
ms.date: 11/04/2016
f1_keywords:
- C3919
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
ms.openlocfilehash: 9f09c9ca29d247162da8f107ceb2ba47ee26bacc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143892"
---
# <a name="compiler-error-c3919"></a>编译器错误 C3919

"event_method"：函数必须是 "type" 类型

未正确声明事件访问器方法。

有关事件的详细信息，请参阅 [事件](../../extensions/event-cpp-component-extensions.md)。

下面的示例生成 C3919：

```cpp
// C3919.cpp
// compile with: /clr /c
using namespace System;
delegate void D(String^);
ref class R {
   event D^ e {
      int add(int);   // C3919
      int remove(int);   // C3919

      void add(D^);   // OK
      void remove(D^);   // OK
   }
};
```
