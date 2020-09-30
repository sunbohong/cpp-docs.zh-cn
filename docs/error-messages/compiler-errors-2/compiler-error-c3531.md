---
title: 编译器错误 C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 4537c6c76814f2aeb8f8d62579caec86785de252
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510138"
---
# <a name="compiler-error-c3531"></a>编译器错误 C3531

"symbol"：其类型包含 "auto" 的符号必须具有初始值设定项

指定的变量没有初始值设定项表达式。

### <a name="to-correct-this-error"></a>更正此错误

1. 当你声明变量时，请指定初始值设定项表达式，如使用等号语法的简单赋值。

## <a name="example"></a>示例

下面的示例生成 C3531，因为变量 `x1` 、 `y1, y2, y3` 和 `z2` 未初始化。

```cpp
// C3531.cpp
// Compile with /Zc:auto
int main()
{
   auto x1;                  // C3531
   auto y1, y2, y3;          // C3531
   auto z1 = 1, z2, z3 = -1; // C3531
   return 0;
}
```

## <a name="see-also"></a>请参阅

[auto 关键字](../../cpp/auto-cpp.md)
