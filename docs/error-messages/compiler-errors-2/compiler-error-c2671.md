---
description: 了解更多：编译器错误 C2671
title: 编译器错误 C2671
ms.date: 11/04/2016
f1_keywords:
- C2671
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
ms.openlocfilehash: ec70961a9ea57920a56f2b460a5e6ed481963233
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282102"
---
# <a name="compiler-error-c2671"></a>编译器错误 C2671

"function"：静态成员函数没有 "this" 指针

**`static`** 成员函数尝试访问 **`this`** 。

下面的示例生成 C2671：

```cpp
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```
