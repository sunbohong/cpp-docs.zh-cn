---
title: div、ldiv、lldiv
description: Microsoft C 运行时库 div、ldiv 和 lldiv 函数计算两个整数值的商和余数。
ms.date: 11/21/2020
api_name:
- div
- ldiv
- lldiv
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- div
- ldiv
- lldiv
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.openlocfilehash: d87b2e3a84e389be8b14970a3aa611bb288cbec8
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440284"
---
# <a name="div-ldiv-lldiv"></a>`div`, `ldiv`, `lldiv`

计算两个整数值的商和余数。

## <a name="syntax"></a>语法

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>参数

*`numer`*\
分子。

*`denom`*\
分母。

## <a name="return-value"></a>返回值

**`div`** 使用类型的参数调用 **`int`** ，返回类型的结构 `div_t` ，该结构包含商和余数。 类型为的参数的返回值 **`long`** 为 `ldiv_t` ，且类型为的参数的返回值 **`long long`** 为 `lldiv_t` 。 `div_t`、 `ldiv_t` 和 `lldiv_t` 类型在中定义 \<stdlib.h> 。

## <a name="remarks"></a>备注

**`div`** 函数除以 *`numer`* *`denom`* 并计算商和余数。 [`div_t`](../../c-runtime-library/standard-types.md)结构包含商、 `quot` 和余数 `rem` 。 商的符号与数学商的符号相同。 它的绝对值是小于数学商的绝对值的最大整数。 如果分母为 0，程序将终止并显示错误消息。

**`div`** 采用或类型参数的重载 **`long`** **`long long`** 仅可用于 c + + 代码。 返回类型 [`ldiv_t`](../../c-runtime-library/standard-types.md) 和 [`lldiv_t`](../../c-runtime-library/standard-types.md) 包含成员 `quot` 和，它们与的 `rem` 成员具有相同的含义 `div_t` 。

## <a name="requirements"></a>要求

| 例程所返回的值 | 必需的标头 |
|--|--|
| **`div`**, **`ldiv`**, **`lldiv`** | \<stdlib.h> |

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`imaxdiv`](imaxdiv.md)
