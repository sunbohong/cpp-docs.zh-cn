---
title: cosh、coshf、coshl
description: 适用于 cosh、coshf 和 coshl 的 API 参考;计算浮点值的双曲余弦值。
ms.date: 1/15/2021
api_name:
- cosh
- coshf
- coshl
- _o_cosh
- _o_coshf
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: c010dcdc30b16f94f55fca99d67b58e5c19370c7
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564090"
---
# <a name="cosh-coshf-coshl"></a>`cosh`, `coshf`, `coshl`

计算双曲余弦值。

## <a name="syntax"></a>语法

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
#define cosh(X) // Requires C11 or higher

float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>参数

*`x`*\
角度（以弧度为单位）。

## <a name="return-value"></a>返回值

的双曲余弦值 *`x`* 。

默认情况下，如果结果在、或调用中太大， **`cosh`** **`coshf`** **`coshl`** 则函数将返回， **`HUGE_VAL`** 并将设置 **`errno`** 为 **`ERANGE`** 。

|输入|SEH 异常|`Matherr` 异常|
|-----------|-------------------|-----------------------|
|± **`QNAN`**, **`IND`**|无|**`_DOMAIN`**|
|*`x`* ≥ 7.104760 e + 002|**`INEXACT`**+**`OVERFLOW`**|**`OVERFLOW`**|

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用 **`cosh`** 采用和返回 **`float`** 或 **`long double`** 值的重载。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`cosh`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `cosh()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-------------|---------------------|-|
|**`coshf`**, **`cosl`**, **`coshl`**|`<math.h>`|`<cmath>` 或 `<math.h>`|
|**`coshf()`** 宏定义 | `<tgmath.h>` ||

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅[ `sinh` 、 `sinhf` 、 `sinhl` ](sinh-sinhf-sinhl.md)中的示例。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`acosh, acoshf, acoshl`](acosh-acoshf-acoshl.md)\
[`asinh, asinhf, asinhl`](asinh-asinhf-asinhl.md)\
[`atanh, atanhf, atanhl`](atanh-atanhf-atanhl.md)\
[`_matherr`](matherr.md)\
[`sinh, sinhf, sinhl`](sinh-sinhf-sinhl.md)\
[`tanh, tanhf, tanhl`](tanh-tanhf-tanhl.md)