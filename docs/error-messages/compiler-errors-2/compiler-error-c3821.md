---
title: 编译器错误 C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 97d6dc0544176d90b90702a7d1f1648e8e98d756
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686621"
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
