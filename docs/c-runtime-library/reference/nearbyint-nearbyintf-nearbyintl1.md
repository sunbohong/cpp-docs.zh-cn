---
title: nearbyint、nearbyintf、nearbyintl
description: 适用于 nearbyint、nearbyintf 和 nearbyintl 的 API 参考;这会将指定的浮点值舍入为整数，并以浮点格式返回该值。
ms.date: 9/1/2020
api_name:
- nearbyint
- nearbyintf
- nearbyintl
- _o_nearbyint
- _o_nearbyintf
- _o_nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: 9717559518032c6f1f2126c7ded7cb90603bce64
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556380"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint、nearbyintf、nearbyintl

将指定的浮点值舍入为整数，并以浮点格式返回该值。

## <a name="syntax"></a>语法

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
#define nearbyint( X ) // Requires C11 or higher

float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>参数

*x-blade*\
要舍入的值。

## <a name="return-value"></a>返回值

如果成功，则返回 *x*，舍入为最接近的整数，使用 [fegetround](fegetround-fesetround2.md)报告的当前舍入格式。 否则，该函数返回以下值之一：

|问题|返回|
|-----------|------------|
|*x* = ±无限大|±无限大，未修改|
|*x* = ±0|±0，未修改|
|*x* = NaN|NaN|

不通过 [_matherr](matherr.md)报告错误;具体而言，此函数不会报告任何 **FE_INEXACT** 异常。

## <a name="remarks"></a>备注

此函数与 [rint](rint-rintf-rintl.md) 之间的主要区别在于，此函数不会引发不精确的浮点异常。

因为最大浮点值均为精确的整数，所以此函数本身不会溢出；而输出可能会溢出返回值，具体取决于所使用函数的版本。

C + + 允许重载，因此你可以调用采用和返回或参数的 **nearbyint** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏来调用此函数，否则 **nearbyint** 始终采用两个双精度值并返回一个双精度值。

如果使用 \<tgmath.h> `nearbyint()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**nearbyint**、 **nearbyintf**、 **nearbyintl**|\<math.h>|\<cmath> 或 \<math.h>|
|**nearbyint** 宏 | \<tgmath.h> ||

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[数学和浮点支持](../floating-point-support.md)<br/>
