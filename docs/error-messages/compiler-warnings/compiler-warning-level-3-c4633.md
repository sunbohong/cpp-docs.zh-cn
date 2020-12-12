---
description: 详细了解：编译器警告 (等级 3) C4633
title: 编译器警告（等级 3）C4633
ms.date: 11/04/2016
f1_keywords:
- C4633
helpviewer_keywords:
- C4633
ms.assetid: 6d76f268-ba8c-448b-8e83-b903a18b583b
ms.openlocfilehash: 3818d0a54f9ebc43b5686eefa73f10f9036a6373
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325941"
---
# <a name="compiler-warning-level-3-c4633"></a>编译器警告（等级 3）C4633

XML 文档注释目标：错误：原因

[\<param>](../../build/reference/param-visual-cpp.md)编译器未找到传递给标记的名称。

下面的示例生成 C4633：

```cpp
// C4633.cpp
// compile with: /clr /doc /LD /W3

/// Text for class MyClass.
public ref class MyClass {
   // C4633 remove line for Int3
   /// <param name="Int1">Used to indicate status.</param>
   /// <param name="Int3">Used to indicate status.</param>
   void MyMethod(int Int1) {
      Int1 = 0;
      Int1++;
   }
};
```
