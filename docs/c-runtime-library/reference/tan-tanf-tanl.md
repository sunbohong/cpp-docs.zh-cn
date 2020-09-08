---
title: tan、tanf、tanl
description: 适用于 tan、tanf 和 tanl 的 API 参考;计算浮点值的正切值。
ms.date: 08/31/2020
api_name:
- tan
- tanf
- tanl
- _o_tan
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
- tan
- tanf
- _tanl
- tanl
helpviewer_keywords:
- tanl function
- _tanl function
- tan function
- calculating tangents
- tangent
- tanf function
- trigonometric functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
ms.openlocfilehash: 8137bf4cbce59083e8e7c09557400fbff4f6b1df
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556536"
---
# <a name="tan-tanf-tanl"></a>tan、tanf、tanl

计算正切值。

## <a name="syntax"></a>语法

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
#define tan(x) // Requires C11 or higher
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
角度（以弧度为单位）。

## <a name="return-value"></a>返回值

**Tan**函数返回*x*的正切值。 如果 *x* 大于或等于263，或者小于或等于-263，则结果中的结果会丢失。

|输入|SEH 异常|**Matherr** 异常|
|-----------|-------------------|-------------------------|
|± QNAN，IND|无|_DOMAIN|
|± INF|**无效**|_DOMAIN|

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此可以调用采用和返回或值的 **茶色** 重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则 **tan** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `tan()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-------------|---------------------|-|
|**tan**、 **tanf**、 **tanl**|\<math.h>|\<cmath> 或 \<math.h>|
|**tan ( # B1 ** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_tan.c
// This program displays the tangent of pi / 4
// Compile by using: cl crt_tan.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x;

   x = tan( pi / 4 );
   printf( "tan( %f ) = %f\n", pi/4, x );
}
```

```Output
tan( 0.785398 ) = 1.000000
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[asin、asinf、asinl](asin-asinf-asinl.md)<br/>
[atan、atanf、atanl、atan2、atan2f、atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[_CItan](../../c-runtime-library/citan.md)<br/>
