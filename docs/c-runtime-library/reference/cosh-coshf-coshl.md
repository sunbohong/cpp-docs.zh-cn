---
title: cosh、coshf、coshl
description: 适用于 cosh、coshf 和 coshl 的 API 参考;计算浮点值的双曲余弦值。
ms.date: 08/31/2020
api_name:
- cosh
- coshf
- coshl
- _o_cosh
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
ms.openlocfilehash: 0ea4a5b77850e196c29519ac49b589a0c2b6c9a7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555522"
---
# <a name="cosh-coshf-coshl"></a>cosh、coshf、coshl

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

*x-blade*\
角度（以弧度为单位）。

## <a name="return-value"></a>返回值

*X*的双曲余弦值。

默认情况下，如果结果在 **cosh**、 **coshf**或 **coshl** 调用中太大，则函数将返回 **HUGE_VAL** ，并将 **errno** 设置为 **ERANGE**。

|输入|SEH 异常|Matherr 异常|
|-----------|-------------------|-----------------------|
|± **QNAN**， **IND**|无|**_DOMAIN**|
|*x* ≥ 7.104760 e + 002|不**精确** +**溢出**|**超出**|

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此可以调用 **cosh** 的重载，该重载采用和返回 **`float`** 或 **`long double`** 值。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **cosh** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `cosh()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-------------|---------------------|-|
|**coshf**、 **cosl**、 **coshl**|\<math.h>|\<cmath> 或 \<math.h>|
|**coshf ( # B1 ** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [sinh、sinhf、sinhl](sinh-sinhf-sinhl.md)中的示例。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[acosh、acoshf、acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh、asinhf、asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh、atanhf、atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh、sinhf、sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh、tanhf、tanhl](tanh-tanhf-tanhl.md)<br/>
