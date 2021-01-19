---
title: logb、logbf、logbl、_logb、_logbf
description: 用于 logb、logbf、logbl、_logb 和 _logbf 的 API 参考;它提取浮点参数的指数值。
ms.date: 1/15/2021
api_name:
- logb
- _logb
- _logbl
- logbf
- _logbf
- logbl
- _o__logb
- _o_logb
- _o_logbf
- _o_logbl
- _o__logbf
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.openlocfilehash: 5d64b315a502f7d1794d7726f14a94ed66a67cd5
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564025"
---
# <a name="logb-logbf-logbl-_logb-_logbf"></a>`logb`, `logbf`, `logbl`, `_logb`, `_logbf`

提取浮点型参数的指数值。

## <a name="syntax"></a>语法

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
#define logb(X) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*`x`*\
浮点值。

## <a name="return-value"></a>返回值

**`logb`** 返回的无偏差指数值返回为以 *`x`* 浮点值形式表示的有符号整数。

## <a name="remarks"></a>备注

**`logb`** 函数提取浮点参数的指数值 *`x`* ，如同 *`x`* 用无限范围表示。 如果参数 *`x`* 为非规范化，则将其视为已规范化。

由于 c + + 允许重载，因此你可以调用 **`logb`** 采用和返回 **`float`** 或 **`long double`** 值的重载。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`logb`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `logb()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

|输入|SEH 异常|`Matherr` 异常|
|-----------|-------------------|-----------------------|
|`± QNAN`,`IND`|无|`_DOMAIN`|
|±0|`ZERODIVIDE`|`_SING`|

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`_logb`**|`<float.h>`|
|**`logb`**, **`logbf`**, **`logbl`**, **`_logbf`**|`<math.h>`|
|**`logb`** 宏定义 | `<tgmath.h>` |

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

[C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`frexp`](frexp.md)