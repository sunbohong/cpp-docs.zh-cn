---
description: 了解详细信息： catanh、catanhf、catanhl
title: catanh、catanhf、catanhl
ms.date: 11/04/2016
api_name:
- catanh
- catanhf
- catanhl
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
- catanh
- catanhf
- catanhl
- complex/catanh
- complex/catanhf
- complex/catanhl
helpviewer_keywords:
- catanh function
- catanhf function
- catanhl function
ms.assetid: 1b6021cb-647a-41b4-9d7f-919cc8b57b86
ms.openlocfilehash: 9f69ee7644c295fe36b0d907d858d33db27f1c99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275160"
---
# <a name="catanh-catanhf-catanhl"></a>catanh、catanhf、catanhl

检索复数的反双曲正切值，并沿实轴的间隔 [-1; + 1] 之外的分支剪切。

## <a name="syntax"></a>语法

```C
_Dcomplex catanh(
   _Dcomplex z
);
_Fcomplex catanh(
   _Fcomplex z
);  // C++ only
_Lcomplex catanh(
   _Lcomplex z
);  //  C++ only
_Fcomplex catanhf(
   _Fcomplex z
);
_Lcomplex catanhl(
   _Lcomplex z
);
```

### <a name="parameters"></a>parameters

*z*<br/>
表示角度的复数（以弧度为单位）。

## <a name="return-value"></a>返回值

*Z* 的反双曲正切值（以弧度表示）。 沿实轴的结果是无限的，并且沿虚轴的间隔 [-i π/2; + i π/2] 中。 如果 *z* 超出间隔 [-1，+ 1]，将出现域错误。 如果 *z* 为-1 或 + 1，则将出现极点错误。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此可以调用 **catanh** 的重载，该重载采用并返回 **_Fcomplex** 和 **_Lcomplex** 值。 在 C 程序中， **catanh** 始终采用并返回 **_Dcomplex** 值。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**catanh**、               **catanhf**、 **catanhl**|\<complex.h>|\<ccomplex>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>
[ctanh、ctanhf、ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan、catanf、catanl](catan-catanf-catanl.md)<br/>
[csinh、csinhf、csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh、casinhf、casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh、ccoshf、ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh、cacoshf、cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos、cacosf、cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan、ctanf、ctanl](ctan-ctanf-ctanl.md)<br/>
[csin、csinf、csinl](csin-csinf-csinl.md)<br/>
[casin、casinf、casinl](casin-casinf-casinl.md)<br/>
[ccos、ccosf、ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt、csqrtf、csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
