---
description: 了解更多：编译器错误 C2317
title: 编译器错误 C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: e83a69086c22349d12d041e3b6dc2fd97a227272
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282218"
---
# <a name="compiler-error-c2317"></a>编译器错误 C2317

在行“number”上开始的“try”块没有 catch 处理程序

**`try`** 块必须具有至少一个 catch 处理程序。

以下示例生成 C2317：

```cpp
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

可能的解决方法：

```cpp
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```
