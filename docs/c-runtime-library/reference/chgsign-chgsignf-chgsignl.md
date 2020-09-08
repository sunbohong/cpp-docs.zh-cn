---
title: _chgsign、_chgsignf、_chgsignl
description: _Chgsign、_chgsignf 和 _chgsignl 的 API 参考;这会反转浮点自变量的符号。
ms.date: 04/05/2018
api_name:
- _chgsignl
- _chgsign
- _chgsignf
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
- _chgsignf
- chgsign
- _chgsignl
- _chgsign
helpviewer_keywords:
- _chgsignl function
- _chgsignf function
- chgsign function
- _chgsign function
ms.assetid: a6646f8e-213d-4564-8617-f43bc66f989f
ms.openlocfilehash: 7dc934f3c2d22cc36abe5f31f7d64e0674ccdd3a
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555196"
---
# <a name="_chgsign-_chgsignf-_chgsignl"></a>_chgsign、_chgsignf、_chgsignl

颠倒浮点型参数的符号。

## <a name="syntax"></a>语法

```C
double _chgsign(
   double x
);
float _chgsignf(
   float x
);
long double _chgsignl(
   long double x
);
```

### <a name="parameters"></a>参数

*x*<br/>
要更改的浮点值。

## <a name="return-value"></a>返回值

**_Chgsign**函数返回一个与浮点参数*x*相同的值，但其符号已反转。 无错误返回。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_chgsign**|\<float.h>|
|**_chgsignf**， **_chgsignl**|\<math.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[fabs、fabsf、fabsl](fabs-fabsf-fabsl.md)<br/>
[copysign、copysignf、copysignl、_copysign、_copysignf、_copysignl](copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)<br/>
