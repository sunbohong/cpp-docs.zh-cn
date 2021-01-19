---
title: tanh、tanhf、tanhl
description: 适用于 tanh、tanhf 和 tanhl 的 API 参考;计算浮点值的双曲正切值。
ms.date: 1/15/2021
api_name:
- tanh
- tanhf
- tanhl
- _o_tanh
- _o_tanhf
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
- tanh
- tanhf
- tanhl
- _tanhl
helpviewer_keywords:
- tanhl function
- _tanhl function
- tanh function
- tanhf function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: c09655b4a86010ff6a476f7dacbce4f9f73ab3cc
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564116"
---
# <a name="tanh-tanhf-tanhl"></a>`tanh`, `tanhf`, `tanhl`

计算双曲正切值。

## <a name="syntax"></a>语法

```C
double tanh( double x );
float tanhf( float x );
long double tanhl( long double x );
#define tanh(x) // Requires C11 or higher
```

```cpp
float tanh( float x );  // C++ only
long double tanh( long double x );  // C++ only
```

### <a name="parameters"></a>参数

*`x`*\
角度（以弧度为单位）。

## <a name="return-value"></a>返回值

**`tanh`** 函数返回的双曲正切值 *`x`* 。 无错误返回。

|输入|SEH 异常|**`Matherr`** 异常|
|-----------|-------------------|-------------------------|
|± `QNAN`,`IND`|无|`_DOMAIN`|

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用 **`tanh`** 采用和返回 **`float`** 或 **`long double`** 值的重载。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`tanh`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `tanh()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C)|
|-------------|---------------------|-|
|**`tanh`**, **`tanhf`**, **`tanhl`**|`<math.h>`|`<cmath>` 或 `<math.h>`|
|**`tanh()`** 宏定义 | `<tgmath.h>` ||

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_tanh.c
// This program displays the tangent of pi / 4
// and the hyperbolic tangent of the result.
// Compile by using: cl crt_tanh.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = tan( pi / 4 );
   y = tanh( x );
   printf( "tan( %f ) = %f\n", pi/4, x );
   printf( "tanh( %f ) = %f\n", x, y );
}
```

```Output
tan( 0.785398 ) = 1.000000
tanh( 1.000000 ) = 0.761594
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`acosh, acoshf, acoshl`](acosh-acoshf-acoshl.md)\
[`asinh, asinhf, asinhl`](asinh-asinhf-asinhl.md)\
[`atanh, atanhf, atanhl`](atanh-atanhf-atanhl.md)\
[`cosh, coshf, coshl`](cosh-coshf-coshl.md)\
[`sinh, sinhf, sinhl`](sinh-sinhf-sinhl.md)