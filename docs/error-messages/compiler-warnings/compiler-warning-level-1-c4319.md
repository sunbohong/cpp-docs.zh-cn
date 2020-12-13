---
description: 了解详细信息：编译器警告 (等级 1) C4319
title: 编译器警告（等级 1）C4319
ms.date: 01/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: af38714ab506fad389d9d2407b5a83aebf01f7c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340055"
---
# <a name="compiler-warning-level-1-c4319"></a>编译器警告（等级 1）C4319

> "~"：将 "*type1*" 扩展到更大的 "*type2*" 时为零

**~** (按位求补) 运算符的结果是无符号的，然后在转换为更大的类型时进行零扩展。

## <a name="example"></a>示例

在下面的示例中， `~(a - 1)` 将作为32位无符号长表达式进行计算，然后将其转换为64位。 这会导致意外的运算结果。

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
