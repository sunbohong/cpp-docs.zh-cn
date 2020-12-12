---
description: 了解更多：编译器错误 C3821
title: 编译器错误 C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 745efeb21933e06f65f9e700ad5780da8234da90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249368"
---
# <a name="compiler-error-c3821"></a>编译器错误 C3821

"function"：托管类型或函数不能用于非托管函数

具有内联程序集或 [setjmp](../../c-runtime-library/reference/setjmp.md) 的函数不能包含值类型或托管类。 若要修复此错误，请删除内联程序集， `setjmp` 或删除托管对象。

如果尝试在 vararg 函数中使用自动存储，也可能会发生 C3821。  有关详细信息，请参阅 [变量参数列表 ( )  (的引用类型的 c + +/cli) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) 和 [c + + Stack 语义](../../dotnet/cpp-stack-semantics-for-reference-types.md)。

## <a name="examples"></a>示例

下面的示例生成 C3821。

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

下面的示例生成 C3821。

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
