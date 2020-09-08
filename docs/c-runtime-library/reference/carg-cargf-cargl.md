---
title: carg、cargf、cargl
description: 适用于 carg、cargf 和 cargl 的 API 参考;这会检索复数的参数，并沿着负实轴进行分支切割。
ms.date: 9/2/2020
api_name:
- carg
- cargf
- cargl
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
- carg
- cargf
- cargl
- complex/carg
- complex/cargf
- complex/cargl
helpviewer_keywords:
- carg function
- cargf function
- cargl function
ms.assetid: 610d6a93-b929-46ab-a966-b77db0b804be
ms.openlocfilehash: 907694904b260c44dde84724c739c62dfe46dbde
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555808"
---
# <a name="carg-cargf-cargl"></a>carg、cargf、cargl

检索复数的参数，其中分支沿负实轴剪切。

## <a name="syntax"></a>语法

```C
double carg(
   _Dcomplex z
);
float carg(
   _Fcomplex z
);  // C++ only
long double carg(
   _Lcomplex z
);  // C++ only
float cargf(
   _Fcomplex z
);
long double cargl(
   _Lcomplex z
);
#define carg(X) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*z*\
一个复数。

## <a name="return-value"></a>返回值

参数 (也称为 *z*) 阶段。 结果以 [-π，+ π] 为间隔。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用 **_Fcomplex**或 **_Lcomplex**值的**carg**重载，以及返回值 **`float`** 或 **`long double`** 值。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **carg** 始终采用 **_Dcomplex** 值并返回 **`double`** 值。

如果使用 \<tgmath.h> `carg()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**carg**、 **cargf**、 **cargl**|\<complex.h>|\<ccomplex>|
|**carg** 宏 | \<tgmath.h> ||

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[norm、normf、norml1](norm-normf-norml1.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
