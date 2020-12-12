---
description: 了解更多：编译器错误 C2362
title: 编译器错误 C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 9043b6e82fd45923e7108d6a6f8934416eaaa328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210915"
---
# <a name="compiler-error-c2362"></a>编译器错误 C2362

> "goto *label*" 跳过了 "*identifier*" 的初始化

使用 [/za](../../build/reference/za-ze-disable-language-extensions.md)进行编译时，跳转到标签可防止初始化该标识符。

如果声明包含在未输入的块中，或者如果该变量已初始化，则只能跳过带有初始值设定项的声明。

下面的示例生成 C2362：

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

可能的解决方法：

```cpp
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```
