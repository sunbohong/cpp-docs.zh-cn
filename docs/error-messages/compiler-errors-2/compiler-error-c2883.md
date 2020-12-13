---
description: 了解更多：编译器错误 C2883
title: 编译器错误 C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 2ff905f5f1ca8fea4f175799e576e4538bbab164
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332347"
---
# <a name="compiler-error-c2883"></a>编译器错误 C2883

"name"：函数声明与 using 声明引入的 "identifier" 冲突

尝试多次定义函数。 第一次定义是从具有声明的命名空间中进行的 **`using`** 。 第二个是本地定义。

下面的示例生成 C2883：

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
