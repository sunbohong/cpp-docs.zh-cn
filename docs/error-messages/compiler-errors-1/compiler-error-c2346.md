---
description: 了解更多：编译器错误 C2346
title: 编译器错误 C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: eb2bbda6c7f7e0c9213b35a794b915967d03321f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298365"
---
# <a name="compiler-error-c2346"></a>编译器错误 C2346

"function" 不能编译为本机：原因

编译器无法将函数编译为 MSIL。

有关详细信息，请参阅 [managed、非托管](../../preprocessor/managed-unmanaged.md) 和 [/Clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

### <a name="to-correct-this-error"></a>更正此错误

1. 删除不能编译为 MSIL 的函数中的代码。

1. 请勿用 **/clr** 编译模块，或将函数标记为非托管杂注的非托管函数。

## <a name="example"></a>示例

下面的示例生成 C2346。

```cpp
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

int main()
{
   S s;
}
```
