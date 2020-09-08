---
title: tgamma、tgammaf、tgammal
description: 适用于 tgamma、tgammaf 和 tgammal 的 API 参考;这会确定指定值的伽玛函数。
ms.date: 9/1/2020
api_name:
- tgamma
- tgammaf
- tgammal
- _o_tgamma
- _o_tgammaf
- _o_tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: b49020ca0697e920dccf188df4ad024820966571
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555171"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma、tgammaf、tgammal

确定指定值的 gamma 函数。

## <a name="syntax"></a>语法

```C
double tgamma(
   double x
);

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

#define tgamma(X) // Requires C11 or higher

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
要查找其伽玛值的值。

## <a name="return-value"></a>返回值

如果成功，则返回 *x*的伽玛。

如果 *x* 的大小太大或数据类型太小，则可能会发生范围错误。 如果 *x* <= 0，则可能出现域错误或范围错误。

|问题|返回|
|-----------|------------|
|x = ±0|±无限大|
|x = 负整数|NaN|
|x =-无限大|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|域错误|NaN|
|极点错误|± HUGE_VAL、± HUGE_VALF 或± HUGE_VALL|
|溢出范围错误|± HUGE_VAL、± HUGE_VALF 或± HUGE_VALL|
|下溢范围错误|舍入后的正确值。|

按 [_matherr](matherr.md) 中所指定的报告错误。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 **tgamma** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **tgamma** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `tgamma()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

如果 x 是自然数，则此函数返回 (x-1) 的阶乘。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**tgamma**、 **tgammaf**、  **tgammal**|\<math.h>|\<cmath>|
|**tgamma** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[lgamma、lgammaf、lgammal](lgamma-lgammaf-lgammal.md)<br/>
