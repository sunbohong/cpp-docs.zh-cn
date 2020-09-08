---
title: creal、crealf、creall
description: 适用于 creal、crealf、creall 的 API 参考检索复数的实部。
ms.date: 9/2/2020
api_name:
- creal
- crealf
- creall
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
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
ms.openlocfilehash: 4f375bbe8813ba67130f8b56d8e2c99d5b734764
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555925"
---
# <a name="creal-crealf-creall"></a>creal、crealf、creall

检索复数的实部。

## <a name="syntax"></a>语法

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
#define creal(X) // Requires C11 or higher

float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>参数

*z*<br/>
一个复数。

## <a name="return-value"></a>返回值

*Z*的实部。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用采用 **_Fcomplex**或 **_Lcomplex**值的**creal**重载，以及返回值 **`float`** 或 **`long double`** 值。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **creal** 始终采用 **_Dcomplex** 值并返回 **`double`** 值。

如果使用 \<tgmath.h> `creal()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**creal**、 **crealf**、 **creall**|\<complex.h>|\<ccomplex>|
|**creal** 宏 | \<tgmath.h> ||

**_Fcomplex**、 **_Dcomplex**和 **_Lcomplex**类型是特定于 Microsoft 的等效项，它们分别是未实现的本机 C99 类型**float _Complex**、 **double _Complex**和**long double _Complex**。 有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[_Cbuild、_FCbuild、_LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[norm、normf、norml1](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
