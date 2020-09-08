---
title: fdim、fdimf、fdiml
description: 适用于 fdim、fdimf 和 fdiml 的 API 参考;这确定了两个值之间的正差。
ms.date: 9/1/2020
api_name:
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
ms.openlocfilehash: 406fc5cfe543aa0865760df9ff780c62e78510fc
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554781"
---
# <a name="fdim-fdimf-fdiml"></a>fdim、fdimf、fdiml

确定第一个值和第二个值之间的正数差。

## <a name="syntax"></a>语法

```C
double fdim(
   double x,
   double y
);

float fdim(
   float x,
   float y
); //C++ only

long double fdim(
   long double x,
   long double y
); //C++ only

float fdimf(
   float x,
   float y
);

long double fdiml(
   long double x,
   long double y
);

#define fdim(X) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
第一个值。

*误差*\
第二个值。

## <a name="return-value"></a>返回值

返回 *x* 和 *y*之间的正差：

|返回值|方案|
|------------------|--------------|
|x-y|如果 x > y|
|0|如果 x <= y|

否则，可能返回以下错误之一：

|问题|返回|
|-----------|------------|
|溢出范围错误|+ HUGE_VAL、+ HUGE_VALF，或 + HUGE_VALL|
|下溢范围错误|正确值（舍入后）|
|*x* 或 *y* 为 NaN|NaN|

按 [_matherr](matherr.md) 中所指定的报告错误。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 **fdim** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **fdim** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `fdim()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

除 NaN 处理外，此函数与等效 `fmax(x - y, 0)` 。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**fdim**、 **fdimf**、 **fdiml**|\<math.h>|\<cmath>|
|**fdim** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[fmax、fmaxf、fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs、labs、llabs、_abs64](abs-labs-llabs-abs64.md)<br/>
