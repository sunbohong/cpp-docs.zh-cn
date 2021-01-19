---
title: modf、modff、modfl
description: 适用于 modf、modff 和 modfl 的 API 参考;将浮点值拆分为小数部分和整数部分。
ms.date: 1/15/2021
api_name:
- modff
- modf
- modfl
- _o_modf
- _o_modff
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.openlocfilehash: fbc68c3369e8b992350534e3baa5f19b0f2a5e39
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564013"
---
# <a name="modf-modff-modfl"></a>`modf`, `modff`, `modfl`

将浮点值拆分为小数部分和整数部分。

## <a name="syntax"></a>语法

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>参数

*`x`*\
浮点值。

*`intptr`*\
指向存储整数部分的指针。

## <a name="return-value"></a>返回值

此函数返回的带符号小数部分 *`x`* 。 无错误返回。

## <a name="remarks"></a>备注

**Modf** 函数将浮点值分解 *`x`* 为小数部分和整数部分，每个部分都具有与相同的符号 *`x`* 。 返回的带符号小数部分 *`x`* 。 整数部分在中存储为浮点值 *`intptr`* 。

**modf** 具有使用流式处理 simd 扩展 2 (SSE2) 的实现。 [`_set_SSE2_enable`](set-sse2-enable.md)有关使用 SSE2 实现的信息和限制，请参阅。

C + + 允许重载，因此你可以调用 **`modf`** 采用和返回 **`float`** 或参数的重载 **`long double`** 。 在 C 程序中， **`modf`** 始终采用两个双精度值并返回一个双精度值。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`modf`**, **`modff`**, **`modfl`**|Ansi-c `<math.h>`<br /><br /> C + +：、 `<cmath>` 或 `<math.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_modf.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y, n;

   x = -14.87654321;      /* Divide x into its fractional */
   y = modf( x, &n );     /* and integer parts            */

   printf( "For %f, the fraction is %f and the integer is %.f\n",
           x, y, n );
}
```

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`frexp`](frexp.md)\
[`ldexp`](ldexp.md)