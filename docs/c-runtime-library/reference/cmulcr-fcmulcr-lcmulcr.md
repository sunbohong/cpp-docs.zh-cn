---
description: 了解详细信息： _Cmulcr、_FCmulcr _LCmulcr
title: _Cmulcr、_FCmulcr、_LCmulcr
ms.date: 03/30/2018
api_name:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
ms.openlocfilehash: ea1dbbcea6890246b1e318da238fb8cc2ee3abb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260717"
---
# <a name="_cmulcr-_fcmulcr-_lcmulcr"></a>_Cmulcr、_FCmulcr、_LCmulcr

将复数与浮点数相乘。

## <a name="syntax"></a>语法

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>parameters

*x*<br/>
要相乘的复杂操作数之一。

*y*<br/>
要相乘的浮点操作数。

## <a name="return-value"></a>返回值

一个 **_Dcomplex**、 **_Fcomplex** 或 **_Lcomplex** 结构，它表示复数 *x* 和 flaoting 数字 *y* 的复杂乘积。

## <a name="remarks"></a>备注

由于内置算术运算符不适用于复杂类型的 Microsoft 实现，因此 **_Cmulcr**、 **_FCmulcr** 和 **_LCmulcr** 函数通过浮点类型简化复杂类型的乘法运算。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**_Cmulcr**、 **_FCmulcr** **_LCmulcr**|\<complex.h>|\<complex.h>|

这些函数是 Microsoft 特定的。 **_Dcomplex**、 **_Fcomplex** 和 **_Lcomplex** 的类型是特定于 Microsoft 的等效项，它们分别针对未实现的 C99 本机类型 **double _Complex**、 **float _Complex** 和 **long double _Complex**。 有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[_Cbuild、_FCbuild、_LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc、_FCmulcc、_LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm、normf、norml1](norm-normf-norml1.md)<br/>
[cproj、cprojf、cprojl](cproj-cprojf-cprojl.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
