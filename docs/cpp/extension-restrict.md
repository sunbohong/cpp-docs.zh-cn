---
title: '`__restrict`'
description: 描述 Microsoft Visual C++ `__restrict` 关键字。
ms.date: 11/6/2020
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.openlocfilehash: f23574f49712928e0095f29a3b88b0c05b185eab
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381566"
---
# `__restrict`

与 **`__declspec` ( [`restrict`](../cpp/restrict.md) )** 修饰符一样， **`__restrict`** 关键字 (两个前导下划线 "_" ) 指示符号在当前范围内没有化名。 **`__restrict`** 关键字 `__declspec (restrict)` 在下列方面与修饰符不同：

- **`__restrict`** 关键字仅对变量有效，且 `__declspec (restrict)` 仅对函数声明和定义有效。

- **`__restrict`**[`restrict`](../c-language/type-qualifiers.md#restrict)在 C99 中从开始，与 c 类似，但 **`__restrict`** 可在 c + + 和 c 程序中使用。

- **`__restrict`** 使用时，编译器不传播变量的非别名属性。 也就是说，如果为 **`__restrict`** 非变量分配变量 **`__restrict`** ，则编译器仍会允许非 __restrict 变量使用别名。 这不同于 C99 C 语言关键字的行为 **`restrict`** 。

通常，如果要影响整个函数的行为，请使用 **`__declspec (restrict)`** 而不是关键字。

为了与早期版本兼容， **`_restrict`** 将作为同义词， **`__restrict`** 除非指定了编译器选项 " [ `/Za` \( 禁用语言扩展")](../build/reference/za-ze-disable-language-extensions.md) 。

在 Visual Studio 2015 及更高版本中， **`__restrict`** 可在 c + + 引用中使用。

> [!NOTE]
> 当用于也具有关键字的变量时 [`volatile`](../cpp/volatile-cpp.md) ， **`volatile`** 将优先使用。

## <a name="example"></a>示例

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)
