---
description: 了解更多：编译器错误 C2429
title: 编译器错误 C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 3c16a2a430e8050103c3903cf1355de089252ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190128"
---
# <a name="compiler-error-c2429"></a>编译器错误 C2429

> "*语言功能*" 需要编译器标志 "*编译器选项*"

语言功能需要特定的编译器选项来提供支持。

如果尝试定义 *复合命名空间*（其中包含一个或多个范围嵌套命名空间名称的命名空间，则从 Visual Studio 2015 Update 5 开始）， **C2429 语言功能 "嵌套命名空间定义" 需要编译器标志 "/std： c + + 17"** 。  (在 Visual Studio 2017 版本15.3 中，需要 **/std： c + + 最新** 开关。 c + + 17 之前的 c + + 中不允许使用 ) 复合命名空间定义。 如果指定了 [/std： c + + 17](../../build/reference/std-specify-language-standard-version.md) 编译器选项，则编译器支持复合命名空间定义：

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual Studio 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
