---
title: copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl
description: 'API ref，用于返回一个值，其大小为一个参数，另一个使用 copysign 的符号（使用） ( # A1'
ms.date: 9/1/2020
api_name:
- copysignf
- copysignl
- _copysignl
- _copysign
- _copysignf
- copysign
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
- _copysignl
- copysign
- copysignf
- _copysign
- copysignl
- _copysignf
helpviewer_keywords:
- copysignl function
- _copysignl function
- copysign function
- _copysignf function
- _copysign function
- copysignf function
ms.assetid: 009216d6-72a2-402d-aa6c-91d924b2c9e4
ms.openlocfilehash: 8f9ffe56e82f6a82da15fde3f8efea60fc1c0f9f
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89554859"
---
# <a name="copysign-copysignf-copysignl-_copysign-_copysignf-_copysignl"></a>copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl

返回一个值，该值具有一个自变量的数值和另一个自变量的符号。

## <a name="syntax"></a>语法

```C
double copysign(
   double x,
   double y
);
float copysign(
   float x,
   float y
); // C++ only
long double copysign(
   long double x,
   long double y
); // C++ only
float copysignf(
   float x,
   float y
); // C++ only
long double copysignl(
   long double x,
   long double y
); // C++ only
double _copysign(
   double x,
   double y
);
long double _copysignl(
   long double x,
   long double y
);
#define copysign(X, Y) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
作为结果的数值返回的浮点值。

*误差*\
作为结果的符号返回的浮点值。

[浮点支持例程](../../c-runtime-library/floating-point-support.md)

## <a name="return-value"></a>返回值

**Copysign**函数返回一个浮点值，该值结合了*x*和*y*符号的大小。 无错误返回。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此可以调用 **copysign** 的重载，该重载采用和返回 **`float`** 或 **`long double`** 值。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **copysign** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `copysign()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_copysign**|\<float.h>|
|**copysign**、 **copysignf**、 **copysignl**、 **_copysignf**、 **_copysignl**|\<math.h>|
|**copysign** 宏 | \<tgmath.h> |

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
[_chgsign、_chgsignf、_chgsignl](chgsign-chgsignf-chgsignl.md)<br/>
