---
title: log1p、log1pf、log1pl2
description: 适用于 log1p、log1pf、log1pl2 的 API 参考它计算1加上指定值的自然对数。
ms.date: 9/1/2020
api_name:
- log1p
- log1pf
- log1pl
- _o_log1p
- _o_log1pf
- _o_log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: 8858d761428d4dad6e3fe836b82041ae92f1827a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556225"
---
# <a name="log1p-log1pf-log1pl"></a>log1p、log1pf、log1pl

计算 1 加上指定值的自然对数。

## <a name="syntax"></a>语法

```C
double log1p(
   double x
);
float log1pf(
   float x
);
long double log1pl(
   long double x
);

#define log1p(X) // Requires C11 or higher

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
浮点型参数。

## <a name="return-value"></a>返回值

如果成功，则返回 (*x* + 1) 的自然 (*e*) 对数。

否则，可能返回以下值之一：

|输入|结果|SEH 异常|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|非规格化数|与输入相同|UNDERFLOW||
|±0|与输入相同|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|± SNaN|与输入相同|INVALID||
|± QNaN，不定|与输入相同|||

如果*x* =-1，则**errno**值设置为 ERANGE。 如果*x* <-1，则将**errno**值设置为**EDOM** 。

## <a name="remarks"></a>备注

**log1p** `log(x + 1)` 当*x*接近0时，log1p 函数可能更准确。

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 **log1p** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **log1p** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `log1p()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

如果 *x* 是自然数，则此函数返回 (*x* -1) 的阶乘的对数。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**log1p**、 **log1pf**、 **log1pl**|\<math.h>|\<cmath>|
|**log1p** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)\
[log2、log2f、log2l](log2-log2f-log2l.md)\
[log、logf、log10、log10f](log-logf-log10-log10f.md)
