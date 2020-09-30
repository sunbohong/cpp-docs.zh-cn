---
title: exp、expf、expl
description: Exp、expf 和 expl 的 API 参考;计算指数的。
ms.date: 08/31/2020
api_name:
- expf
- expl
- exp
- _o_exp
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
- _expl
- expf
- expl
- exp
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
ms.openlocfilehash: f6733f293f1c8f78e8143d9fdd395013147bbe83
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502103"
---
# <a name="exp-expf-expl"></a>exp、expf、expl

计算指数。

## <a name="syntax"></a>语法

```C
double exp(
   double x
);
float exp(
   float x
);  // C++ only
long double exp(
   long double x
);  // C++ only
float expf(
   float x
);
long double expl(
   long double x
);
#define exp(z) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
用于 exponentiate 自然 *对数的浮点* 值。

## <a name="return-value"></a>返回值

如果成功， **exp** 函数将返回浮点参数 *x*的指数值。 也就是说，结果为 *e*<sup>*x*</sup>，其中 *e* 是自然对数的底数。 溢出时，函数将返回 INF (无穷) 在下溢时， **exp** 返回0。

|输入|SEH 异常|Matherr 异常|
|-----------|-------------------|-----------------------|
|± Quiet NaN、不确定|None|_DOMAIN|
|±无限大|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

**Exp**函数具有使用流式处理 simd 扩展 2 (SSE2) 的实现。 有关使用 SSE2 实现的信息和限制，请参阅 [_set_SSE2_enable](set-sse2-enable.md)。

## <a name="remarks"></a>注解

C + + 允许重载，因此你可以调用采用或参数的 **exp** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则 **exp** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `exp()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的 C 标头|必需的 C++ 标头|
|--------------|---------------------|---|
|**exp**、 **expf**、 **expl**|\<math.h>|\<cmath> 或 \<math.h>|
|**exp** 宏| \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_exp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.302585093, y;

   y = exp( x );
   printf( "exp( %f ) = %f\n", x, y );
}
```

```Output
exp( 2.302585 ) = 10.000000
```

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
