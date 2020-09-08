---
title: fma、fmaf、fmal
description: Fma、fmaf 和 fmal 的 API 参考;这会将两个值相乘，添加第三个值，然后对结果进行舍入，而不会因中间舍入而丢失任何精度。
ms.date: 9/1/2020
api_name:
- fma
- fmaf
- fmal
- _o_fma
- _o_fmaf
- _o_fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: e9ae92c28f24b6281d73450c7cabaad775a84d42
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556692"
---
# <a name="fma-fmaf-fmal"></a>fma、fmaf、fmal

将两个值相乘，添加第三个值，然后对结果进行舍入，而不会因中间舍入而丢失任何精度。

## <a name="syntax"></a>语法

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);

#define fma(X, Y, Z) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
要相乘的第一个值。

*误差*\
要相乘的第二个值。

*z*\
要相加的值。

## <a name="return-value"></a>返回值

返回 `(x * y) + z`。 然后使用当前舍入格式舍入返回值。

否则，可能返回以下值之一：

|问题|返回|
|-----------|------------|
|*x* = 无限大、 *y* = 0 或<br /><br /> *x* = 0、 *y* = 无限大|NaN|
|*x* 或 *y* = 精确的±无限大， *z* = 无穷大，正负号|NaN|
|*x* 或 *y* = NaN|NaN|
|not (*x* = 0， *y*= 不定) ， *z* = NaN<br /><br /> not (*x*= 不定， *y*= 0) ， *z* = NaN|NaN|
|溢出范围错误|± HUGE_VAL、± HUGE_VALF 或± HUGE_VALL|
|下溢范围错误|舍入后的正确值。|

按 [_matherr](matherr.md) 中所指定的报告错误。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 **fma** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则 **fma** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `fma()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

此函数计算值就好像它采取了无限精度，然后将最终结果舍入。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**fma**、 **fmaf**、 **fmal**|\<math.h>|\<cmath>|
|**fma** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
