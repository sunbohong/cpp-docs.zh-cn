---
title: fmax、fmaxf、fmaxl
description: 适用于 fmax、fmaxf 和 fmaxl 的 API 参考;它确定了两个数值中较大的一个。
ms.date: 9/1/2020
api_name:
- fmax
- fmaxf
- fmaxl
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 4f38db64b30598e7cfb4eb4d0f57dccf257dabc5
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556679"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax、fmaxf、fmaxl

确定两个指定数字值的较大值。

## <a name="syntax"></a>语法

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
   long double x,
   long double y
);

#define fmax(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
要比较的第一个值。

*误差*\
要比较的第二个值。

## <a name="return-value"></a>返回值

如果成功，则返回 *x* 或 *y*中较大的一个。 返回的为准确值，且不依赖于任何形式的舍入。

否则，可能返回以下值之一：

|问题|返回|
|-----------|------------|
|*x* = NaN|*y*|
|*y* = NaN|*x*|
|*x* 和 *y* = NaN|NaN|

此函数不使用 [_matherr](matherr.md) 中指定的错误。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 fmax 的重载 `float` `long double` 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则 `fmax` 始终采用并返回双精度型。

如果使用 \<tgmath.h> `fmax()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**fmax**、 **fmaxf**、 **fmaxl**|\<math.h>|\<cmath> 或 \<math.h>|
|**fmax** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[fmin、fminf、fminl](fmin-fminf-fminl.md)<br/>
