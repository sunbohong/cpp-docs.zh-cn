---
title: hypot、hypotf、hypotl、_hypot、_hypotf、_hypotl
description: 用于 hypot、hypotf、hypotl、_hypot、_hypotf 和 _hypotl 的 API 参考;计算斜边的。
ms.date: 9/1/2020
api_name:
- _hypotf
- hypot
- hypotf
- _hypot
- _hypotl
- hypotl
- _o__hypot
- _o__hypotf
- _o_hypot
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
- hypotf
- hypotl
- _hypotl
- hypot
- _hypot
- _hypotf
helpviewer_keywords:
- hypotenuse calculation
- hypot function
- hypotf function
- triangles, calculating hypotenuse
- hypotl function
- calculating hypotenuses
- _hypot function
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
ms.openlocfilehash: 199e330dcd78c372a0279cac9f0e96cb47c561e8
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556445"
---
# <a name="hypot-hypotf-hypotl-_hypot-_hypotf-_hypotl"></a>hypot、hypotf、hypotl、_hypot、_hypotf、_hypotl

计算斜边。

## <a name="syntax"></a>语法

```C
double hypot(
   double x,
   double y
);
float hypotf(
   float x,
   float y
);
long double hypotl(
   long double x,
   long double y
);
double _hypot(
   double x,
   double y
);
float _hypotf(
   float x,
   float y
);
long double _hypotl(
   long double x,
   long double y
);
#define hypotf(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x*、 *y*\
浮点值。

## <a name="return-value"></a>返回值

如果成功， **hypot** 将返回斜边的长度;溢出时， **hypot** 将返回 INF (无限大) 并且 **errno** 变量设置为 **ERANGE**。 您可以使用 **_matherr** 修改错误处理。

有关返回代码的详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**Hypot**函数计算直角三角形的斜边的长度（给定两侧*x*和*y*的长度） (换言之， *x*<sup>2</sup>  +  *y*<sup>2</sup>) 的平方根。

提供的带有前导下划线的函数版本便于与早期的标准兼容。 它们的行为与没有前导下划线的版本相同。 我们建议将不带前导下划线的版本用于新代码。

如果使用 \<tgmath.h> `hypot()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**hypot**、 **hypotf**、 **hypotl**、 **_hypot**、 **_hypotf** **_hypotl**|\<math.h>|
|**hypot** 宏 | \<tgmath.h> |

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_hypot.c
// This program prints the hypotenuse of a right triangle.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 3.0, y = 4.0;

   printf( "If a right triangle has sides %2.1f and %2.1f, "
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );
}
```

```Output
If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[_matherr](matherr.md)<br/>
