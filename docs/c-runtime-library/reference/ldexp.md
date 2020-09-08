---
title: ldexp、ldexpf、ldexpl
description: 适用于 ldexp、ldexpf 和 ldexpl 的 API 参考;这会将浮点数乘以二的整数幂。
ms.date: 9/1/2020
api_name:
- ldexp
- ldexpf
- ldexpl
- _ldexpl
- _o_ldexp
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
- ldexp
- ldexpf
- ldexpl
- _ldexpl
helpviewer_keywords:
- calculating real numbers
- computing real numbers
- mantissas, floating-point variables
- ldexp function
- ldexpf function
- ldexpl function
- exponent, floating-point numbers
- floating-point functions, mantissa and exponent
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
ms.openlocfilehash: 6ce6bcbc8adbc62e8d8598b97a6f77e04fee1511
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555444"
---
# <a name="ldexp-ldexpf-ldexpl"></a>ldexp、ldexpf、ldexpl

将浮点数乘以二的整数幂。

## <a name="syntax"></a>语法

```C
double ldexp(
   double x,
   int exp
);
float ldexpf(
   float x,
   int exp
);
long double ldexpl(
   long double x,
   int exp
);
#define ldexp(X, INT) // Requires C11 or higher

float ldexp(
   float x,
   int exp
);  // C++ only
long double ldexp(
   long double x,
   int exp
);  // C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
浮点值。

*.exp*\
整数指数。

## <a name="return-value"></a>返回值

如果成功， **ldexp** 函数将返回 *x* \* 2<sup>*exp*</sup> 的值。 溢出时，根据 *x*的符号， **ldexp** 返回 +/- **HUGE_VAL**; **errno** 值设置为 **ERANGE**。

有关 **errno** 和可能的错误返回值的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用或类型的 **ldexp** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏来调用此函数，否则， **ldexp** 始终采用 **`double`** 和 **`int`** 并返回 **`double`** 。

如果使用 \<tgmath.h> `ldexp()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**ldexp**、 **ldexpf**、 **ldexpl**|\<math.h>|\<cmath>|
|**ldexp** 宏 | \<tgmath.h> ||

有关兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_ldexp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 4.0, y;
   int p = 3;

   y = ldexp( x, p );
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );
}
```

## <a name="output"></a>Output

```Output
4.0 times two to the power of 3 is 32.0
```

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[modf、modff、modfl](modf-modff-modfl.md)<br/>
