---
title: ilogb、ilogbf、ilogbl2
description: 适用于 ilogb、ilogbf 和 ilogbl2 的 API 参考;这会检索一个整数，该整数表示指定值的无偏差底数2指数。
ms.date: 9/1/2020
api_name:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
ms.openlocfilehash: b27c329cca1edb9d30bb6b9b641f94d174c9c406
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556367"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb、ilogbf、ilogbl

检索一个整数，以表示指定值以 2 为底的无偏差指数。

## <a name="syntax"></a>语法

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);

#define ilogbl(X) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
指定的值。

## <a name="return-value"></a>返回值

如果成功，则返回 *x* 的以2为底的指数作为 **`signed int`** 值。

否则，将返回中定义的以下值之一 \<math.h> ：

|输入|结果|
|-----------|------------|
|±0|FP_ILOGB0|
|± inf，± nan，不定|FP_ILOGBNAN|

按 [_matherr](matherr.md) 中所指定的报告错误。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 **ilogb** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **ilogb** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `ilogb()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

调用此函数类似于调用等效的 **logb** 函数，然后将返回值强制转换为 **`int`** 。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**ilogb**、 **ilogbf**、 **ilogbl**|\<math.h>|\<cmath>|
|**ilogb** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb、logbf、logbl、_logb、_logbf](logb-logbf-logbl-logb-logbf.md)<br/>
