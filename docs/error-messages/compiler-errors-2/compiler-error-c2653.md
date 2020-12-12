---
description: 了解更多：编译器错误 C2653
title: 编译器错误 C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: f3be7ade8a6dcfc6aa8c5a83cc8a055fc230789d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286145"
---
# <a name="compiler-error-c2653"></a>编译器错误 C2653

> "*identifier*"：不是类或命名空间名称

语言语法要求在此处使用类、结构、联合或命名空间名称。

如果你使用的名称尚未在作用域运算符前面声明为类、结构、联合或命名空间，则会发生此错误。 若要解决此问题，请声明名称或在使用之前包含声明该名称的标头。

如果尝试定义 *复合命名空间*（包含一个或多个范围嵌套命名空间名称的命名空间），也可以使用 C2653。 C + + 17 之前的 c + + 中不允许使用复合命名空间定义。 当你指定 [/std： c + + 最新](../../build/reference/std-specify-language-standard-version.md) 编译器选项时，从 Visual Studio 2015 Update 3 开始支持复合命名空间。 从 Visual Studio 2017 版本15.5 开始，当指定 [/std： c + + 17](../../build/reference/std-specify-language-standard-version.md) 选项时，编译器支持复合命名空间定义。

## <a name="examples"></a>示例

此示例生成 C2653，因为使用了作用域名称，但未声明。 在范围运算符 (：： ) 之前，编译器需要使用类、结构、联合或命名空间名称。

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

在未编译为 c + + 17 或更高版本标准的代码中，嵌套命名空间必须在每个嵌套级别使用显式命名空间声明：

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual Studio 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
