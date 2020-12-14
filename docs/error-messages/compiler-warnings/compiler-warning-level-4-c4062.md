---
description: 详细了解：编译器警告 (级别 4) C4062
title: 编译器警告（等级 4）C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: 3aee4286fb8d06d98617ea6fa71929768cbd23c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262043"
---
# <a name="compiler-warning-level-4-c4062"></a>编译器警告（等级 4）C4062

> 未处理枚举 "*enumeration*" 的 switch 中的枚举器 "*identifier*"

枚举器 *标识符* `case` 在语句中没有关联的处理程序 **`switch`** ，并且没有 **`default`** 可以捕获它的标签。 缺少的事例可能是监督，这是代码中的潜在错误。 有关包含事例的语句中未使用的枚举器的相关警告 **`switch`** **`default`** ，请参阅 [C4061](compiler-warning-level-4-c4061.md)。

默认情况下，此警告处于关闭状态。 有关如何启用默认情况下处于关闭状态的警告的详细信息，请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

## <a name="example"></a>示例

下面的示例生成 C4062，并演示如何修复此问题：

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>请参阅

[编译器警告 (等级 4) C4061](compiler-warning-level-4-c4061.md)
