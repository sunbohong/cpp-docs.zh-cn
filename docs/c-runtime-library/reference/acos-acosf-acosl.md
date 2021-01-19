---
title: acos、acosf、acosl
description: 适用于 acos、acosf 和 acosl 的 API 参考;计算浮点值的反余弦值。
ms.date: 1/15/2021
api_name:
- acosf
- acos
- acosl
- _o_acos
- _o_acosf
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
- acos
- acosl
- acosf
- math/acosf
- math/acosl
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.openlocfilehash: 63a9c9577e252c506191b7a49ec9da6502968095
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563830"
---
# <a name="acos-acosf-acosl"></a>`acos`, `acosf`, `acosl`

计算反余弦值。

## <a name="syntax"></a>语法

```C
double acos( double x );
float acosf( float x );
long double acosl( long double x );
#define acos(X) // Requires C11 or higher

float acos( float x );   // C++ only
long double acos( long double x );   // C++ only
```

### <a name="parameters"></a>参数

*`x`*\
介于-1 和1之间的值，计算反余弦的反余弦 () 。

## <a name="return-value"></a>返回值

**`acos`** 函数返回0到π弧度范围内 *x* 的反余弦。

默认情况下，如果 *`x`* 小于-1 或大于1，则 **`acos`** 返回无限期的。

|输入|`SEH` 异常|`Matherr` 异常|
|-----------|-------------------|-----------------------|
|`± ∞`|`INVALID`|`_DOMAIN`|
|`± QNAN, IND`|无|`_DOMAIN`|
|&#124;`x`&#124;>1|`INVALID`|`_DOMAIN`|

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用 **`acos`** 采用并返回 **`float`** 和类型的的重载 **`long double`** 。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`acos`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `acos()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|可选标头|
|-------------|---------------------|----------------------|
|**`acos`**, **`acosf`**, **`acosl`**|`<math.h>`|`<errno.h>`|
|**`acos()`** 宏定义 | `<tgmath.h>` ||

## <a name="example"></a>示例

此程序提示 -1 到 1 范围内的值。 此范围之外的输入值将产生 `_DOMAIN` 错误消息。 如果输入了有效值，此程序将输出该值的反正弦值和反余弦值。

```C
// crt_asincos.c
// arguments: 0

#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int ac, char* av[] )
{
    double  x,
            y;
    errno_t err;

    // argument checking
    if (ac != 2)
    {
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",
                   av[0]);
        return 1;
    }

    // Convert argument into a double value
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)
    {
        fprintf_s( stderr, "Error converting argument into ",
                   "double value.\n");
        return 1;
    }

    // Arcsine of X
    y = asin( x );
    printf_s( "Arcsine of %f = %f\n", x, y );

    // Arccosine of X
    y = acos( x );
    printf_s( "Arccosine of %f = %f\n", x, y );
}
```

```Output
Arcsine of 0.000000 = 0.000000
Arccosine of 0.000000 = 1.570796
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`asin`, `asinf`, `asinl`](asin-asinf-asinl.md)\
[`atan`, `atanf`, `atanl`, `atan2`, `atan2f`, `atan2l`](atan-atanf-atanl-atan2-atan2f-atan2l.md)\
[`cos`, `cosf`, `cosl`](cos-cosf-cosl.md)\
[`_matherr`](matherr.md)\
[`sin`, `sinf`, `sinl`](sin-sinf-sinl.md)\
[`tan`, `tanf`, `tanl`](tan-tanf-tanl.md)