---
title: frexp、frexpf、frexpl
description: 适用于 frexp、frexpf 和 frexpl 的 API 参考;它获取浮点数的尾数和指数。
ms.date: 9/1/2020
api_name:
- frexp
- _o_frexp
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
- frexp
- _frexpl
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
ms.openlocfilehash: a23de4160abcfab2518125bfa0fd35a389901674
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555743"
---
# <a name="frexp-frexpf-frexpl"></a>frexp、frexpf、frexpl

获取浮点数的尾数和指数。

## <a name="syntax"></a>语法

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
#define frexpl(X, INT_PTR) // Requires C11 or higher
```

```cpp
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
浮点值。

*expptr*\
指向存储的整数指数的指针。

## <a name="return-value"></a>返回值

**frexp** 返回尾数。 如果 *x* 为0，则函数对于尾数和指数都返回0。 如果 *expptr* 为 **NULL**，则将调用无效参数处理程序，如 [参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则此函数会将 **errno** 设置为 **EINVAL** ，并返回0。

## <a name="remarks"></a>备注

**Frexp**函数将 (*x*) 的浮点值分解为尾数 (*m*) 和指数 (*n*) ，以便*m*的绝对值大于或等于0.5 且小于1.0， *x*  =  *m* * 2<sup>*n*</sup>。 整数指数 *n* 存储在 *expptr*所指向的位置。

C + + 允许重载，因此可以调用 **frexp**的重载。 在 C 程序中，除非你使用 \<tgmath.h> 宏来调用此函数，否则， **frexp** 始终采用 **`double`** 和 **`int`** 指针并返回 **`double`** 。

如果使用 \<tgmath.h> `frexp()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**frexp**、 **frexpf**、 **frexpl**|\<math.h>|
|**frexp** 宏 | \<tgmath.h> |

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf、modff、modfl](modf-modff-modfl.md)<br/>
