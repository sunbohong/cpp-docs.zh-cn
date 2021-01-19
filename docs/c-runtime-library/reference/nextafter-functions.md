---
title: nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf、nexttowardl
description: 用于 nextafter、nextafterf、nextafterl、_nextafter、_nextafterf、nexttoward、nexttowardf 和 nexttowardl 的 API 参考;这会返回下一个可表示的浮点值。
ms.date: 1/15/2021
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
- _o__nextafter
- _o_nextafter
- _o_nextafterf
- _o_nextafterl
- _o_nexttoward
- _o_nexttowardf
- _o_nexttowardl
- _o__nextafterf
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.openlocfilehash: 664ddb204fa089f83acebf6a9042b17a776ea306
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564129"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>`nextafter`, `nextafterf`, `nextafterl`, `_nextafter`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`

返回下一个可表示的浮点值。

## <a name="syntax"></a>语法

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

#define nextafter(X, Y) // Requires C11 or higher

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );

#define nexttoward(X, Y) // Requires C11 or higher

float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>参数

*`x`*\
要从其开始的浮点值。

*`y`*\
要达到的浮点值。

## <a name="return-value"></a>返回值

返回后返回类型的下一个可表示的浮点值 *`x`* *`y`* 。 如果 *`x`* 和 *`y`* 相等，则函数返回 *`y`* ，转换为返回类型，并且不会触发异常。 如果不 *`x`* 等于 *`y`* ，并且结果为 denormal 或零，则 **`FE_UNDERFLOW`** **`FE_INEXACT`** 将设置和浮点异常状态，并返回正确的结果。 如果 *`x`* 或 *`y`* 为 NAN，则返回值为输入 nan 之一。 如果 *`x`* 是有限的，并且结果是无限的，或者不能在类型中表示，则返回一个正确的带符号无穷大或 NAN， **`FE_OVERFLOW`** 并 **`FE_INEXACT`** 设置和浮点异常状态，并将 **`errno`** 设置为 **`ERANGE`** 。

## <a name="remarks"></a>备注

**`nextafter`** 和 **`nexttoward`** 函数系列是等效的，但的参数类型除外 *`y`* 。 如果 *`x`* 和 *`y`* 相等，则返回的值将 *`y`* 转换为返回类型。

由于 c + + 允许重载，因此，如果包括， `<cmath>` 则可以调用 **`nextafter`** **`nexttoward`** 返回 **`float`** 和类型的和的重载 **`long double`** 。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数， **`nextafter`** 并且 **`nexttoward`** 始终返回 **`double`** 。

如果使用 `<tgmath.h>` `nextafter()` 或 `nexttoward()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

**_Nextafter** 和 **_Nextafterf** 函数是 Microsoft 特定的。 只有在编译 x64 时， **_nextafterf** 函数才可用。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-------------|---------------------------|-------------------------------|
|**`nextafter`**, **`nextafterf`**, **`nextafterl`**, **`_nextafterf`**, **`nexttoward`**, **`nexttowardf`**, **`nexttowardl`**|`<math.h>`|`<math.h>` 或 `<cmath>`|
|**`_nextafter`**|`<float.h>`|`<float.h>` 或 `<cfloat>`|
|**`nextafter`** 宏，  **`nexttoward`** 宏| `<tgmath.h>` ||

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`isnan`, `_isnan`, `_isnanf`](isnan-isnan-isnanf.md)
