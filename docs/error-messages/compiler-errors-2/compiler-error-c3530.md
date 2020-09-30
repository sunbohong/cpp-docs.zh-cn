---
title: 编译器错误 C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 152157824cb270f32b1233f39225abab7741eda5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507055"
---
# <a name="compiler-error-c3530"></a>编译器错误 C3530

"auto" 不能与任何其他类型说明符组合

类型说明符与关键字一起使用 **`auto`** 。

### <a name="to-correct-this-error"></a>更正此错误

1. 不要在使用关键字的变量声明中使用类型说明符 **`auto`** 。

## <a name="example"></a>示例

下面的示例将生成 C3530，因为变量 `x` 同时用 **`auto`** 关键字和类型声明 **`int`** ，并且该示例是用 **/zc： auto**编译的。

```cpp
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>请参阅

[auto 关键字](../../cpp/auto-cpp.md)
