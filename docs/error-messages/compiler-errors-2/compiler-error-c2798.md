---
description: 了解更多：编译器错误 C2798
title: 编译器错误 C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: d3a78eaf09797d658c64b5659dcd0e05191fab1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297585"
---
# <a name="compiler-error-c2798"></a>编译器错误 C2798

"super：： member" 不明确

多个继承结构包含用 [super](../../cpp/super.md)引用的成员。 可以通过以下任一方法修复错误：

- 从 D 的继承列表中删除 B1 或 B2。

- 更改 B1 或 B2 中的数据成员的名称。

下面的示例生成 C2798：

```cpp
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```
