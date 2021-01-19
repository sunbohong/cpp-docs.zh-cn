---
title: sinh、sinhf、sinhl
description: 用于计算浮点值的双曲正弦值的 API 参考。
ms.date: 1/15/2021
api_name:
- sinh
- sinhl
- sinhf
- sinhl
- _o_sinh
- _o_sinhf
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
- sinh
- sinhf
- sinhl
helpviewer_keywords:
- sinh function
- sinhl function
- sinhf function
- calculating hyperbolic sines
- trigonometric functions
- sinhf function
- sinhl function
- hyperbolic functions
ms.openlocfilehash: 73f7210105419c4b8cb9a6e47e5c5f0e43437738
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563791"
---
# <a name="sinh-sinhf-sinhl"></a>`sinh`, `sinhf`, `sinhl`

计算双曲正弦值。

## <a name="syntax"></a>语法

```C
double sinh(double x);
float sinhf(float x);
long double sinhl(long double x);
#define sinh(x) // Requires C11 or higher

float sinh(float x);  // C++ only
long double sinh(long double x);  // C++ only
```

### <a name="parameters"></a>参数

*`x`*\
角度（以弧度为单位）。

## <a name="return-value"></a>返回值

**`sinh`** 函数返回的双曲正弦值 *`x`* 。 默认情况下，如果结果太大，则 **`sinh`** 将设置 **`errno`** 为 **`ERANGE`** 并返回± **`HUGE_VAL`** 。

|输入|SEH 异常|`Matherr` 异常|
|-----------|-------------------|-----------------------|
|± `QNAN`,`IND`|无|`_DOMAIN`|
|&#124;x&#124; ≥ 7.104760 e + 002|`OVERFLOW+INEXACT`|`OVERFLOW`|

有关返回代码的详细信息，请参阅[ `errno` 、、 `_doserrno` `_sys_errlist` 和 `_sys_nerr` ](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用 **`sinh`** 采用和返回 **`float`** 或 **`long double`** 值的重载。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`sinh`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `sinh()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-|-|-|
|**`sinh`**, **`sinhf`**, **`sinhl`**|`<math.h>`|`<cmath>` 或 `<math.h>`|
|**`sinh()`** 宏定义 | `<tgmath.h>` ||

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_sinhcosh.c
// This program displays the hyperbolic
// sine and hyperbolic cosine of pi / 2.
// Compile by using: cl /W4 crt_sinhcosh.c

#include <math.h>
#include <stdio.h>

int main( void)
{
   double pi = 3.1415926535;
   double x, y;

   x = pi / 2;
   y = sinh( x );
   printf( "sinh( %f ) = %f\n",x, y );
   y = cosh( x );
   printf( "cosh( %f ) = %f\n",x, y );
}
```

```Output
sinh( 1.570796 ) = 2.301299
cosh( 1.570796 ) = 2.509178
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`acosh`, `acoshf`, `acoshl`](acosh-acoshf-acoshl.md)\
[`asinh`, `asinhf`, `asinhl`](asinh-asinhf-asinhl.md)\
[`atanh`, `atanhf`, `atanhl`](atanh-atanhf-atanhl.md)\
[`cosh`, `coshf`, `coshl`](cosh-coshf-coshl.md)\
[`tanh`, `tanhf`, `tanhl`](tanh-tanhf-tanhl.md)