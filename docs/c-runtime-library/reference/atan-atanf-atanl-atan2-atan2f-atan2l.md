---
title: atan、atanf、atanl、atan2、atan2f、atan2l
description: 适用于 atan、atanf、atanl、atan2、atan2f 和 atan2l 的 API 参考;计算浮点值的反正切值。
ms.date: 08/31/2020
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
- _o_atan2f
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
ms.openlocfilehash: 1f1d33aac86d94ab3731dd5cf5b124af99ccb3f2
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555625"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan、atanf、atanl、atan2、atan2f、atan2l

计算**x** (**atan**、 **atanf**和**atanl**) 的反正切值，或**y** / **x** (**atan2**、 **atan2f**和**atan2l**) 的反正切值。

## <a name="syntax"></a>语法

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );
#define atan(X) // Requires C11 or higher

float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
#define atan2(Y, X) // Requires C11 or higher

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>参数

*x*、 *y*\
任意数字。

## <a name="return-value"></a>返回值

**atan** 返回 *x* 的反正切值，范围为-π/2 到π/2 弧度。 **atan2**返回*y* / 范围-π到π弧度的 y*x*的反正切值。 如果 *x* 为0，则 **atan** 将返回0。 如果 **atan2** 的两个参数均为0，则该函数返回0。 所有结果都都以弧度为单位。

**atan2** 使用两个参数的符号来确定返回值的象限。

|输入|SEH 异常|Matherr 异常|
|-----------|-------------------|-----------------------|
|± **QNAN**， **IND**|无|**_DOMAIN**|

## <a name="remarks"></a>备注

**Atan**函数计算*x*的反正切函数) 的反正切 (。 **atan2**计算*y* / *x* (的反正切值。如果*x*等于0，则如果*y*为正值，则**atan2**返回π/2;*如果 y*为负，则返回-π/2; 如果*y*为0，则返回 0 ) 。

如果使用 \<tgmath.h> `atan()` 或 `atan2()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

**atan** 具有使用流式处理 simd 扩展 2 (SSE2) 的实现。 有关使用 SSE2 实现的信息和限制，请参阅 [_set_SSE2_enable](set-sse2-enable.md)。

由于 c + + 允许重载，因此你可以调用采用或参数的 **atan** 和 **atan2** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非你使用 \<tgmath.h> 宏来调用此函数，否则， **atan** 和 **atan2** 始终采用 **`double`** 参数并返回 **`double`** 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-------------|---------------------|-|
|**atan**、 **atan2**、 **atanf**、 **atan2f**、 **atanl**、 **atan2l**|\<math.h>|\<cmath> 或 \<math.h>|
|**atan ( # B1 **， **atan2** 宏 | \<tgmath.h> ||

## <a name="example"></a>示例

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[acos、acosf、acosl](acos-acosf-acosl.md)<br/>
[asin、asinf、asinl](asin-asinf-asinl.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
[tan、tanf、tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
