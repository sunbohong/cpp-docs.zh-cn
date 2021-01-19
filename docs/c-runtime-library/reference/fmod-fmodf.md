---
title: fmod、fmodf、fmodl
description: 适用于 fmod、fmodf 和 fmodl 的 API 参考;计算浮点余数的。
ms.date: 1/15/2021
api_name:
- fmod
- fmodf
- fmodl
- _o_fmod
- _o_fmodf
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fmod
- _fmodl
- fmodf
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.openlocfilehash: 8d2c3bcb0f871eb707f264478c4ce492bbb9c80c
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563933"
---
# <a name="fmod-fmodf-fmodl"></a>`fmod`, `fmodf`, `fmodl`

计算浮点余数。

## <a name="syntax"></a>语法

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);

#define fmod(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*`x`*, *`y`*\
浮点值。

## <a name="return-value"></a>返回值

**`fmod`** 返回的浮点余数 *`x`*  /  *`y`* 。 如果的值 *`y`* 为0.0，则 **`fmod`** 返回静默的 NaN。 有关系列的 quiet NaN 表示形式的信息 **`printf`** ，请参阅 [printf](printf-printf-l-wprintf-wprintf-l.md)。

## <a name="remarks"></a>备注

**`fmod`** 函数计算的浮点余数 *f* *`x`*  /  *`y`* *`x`*  =   \* *`y`*  +  *`f`* ，其中， *`i`* 是一个整数，其 *`f`* 符号与相同 *`x`* ，并且的绝对值 *`f`* 小于的绝对值 *`y`* 。

C + + 允许重载，因此你可以调用 **`fmod`** 采用并返回 **`float`** 和值的重载 **`long double`** 。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`fmod`** 始终采用两个参数， **`double`** 并返回 **`double`** 。

如果使用 `<tgmath.h>` `fmod()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**`fmod`**, **`fmodf`**, **`fmodl`**|`<math.h>`|
|**`fmod`** 宏定义 | `<tgmath.h>` |

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`ceil, ceilf, ceill`](ceil-ceilf-ceill.md)\
[`fabs, fabsf, fabsl`](fabs-fabsf-fabsl.md)\
[果`loor, floorf, floorl`](floor-floorf-floorl.md)\
[`_CIfmod`](../../c-runtime-library/cifmod.md)