---
title: cexp、cexpf、cexpl
description: 适用于 cexp、cexpf 和 cexpl 的 API 参考;它计算复数的以 e 为底的指数。
ms.date: 11/04/2016
api_name:
- cexp
- cexpf
- cexpl
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
- cexp
- cexpf
- cexpl
- complex/cepx
- complex/cexpf
- complex/cexpl
helpviewer_keywords:
- cexp function
- cexpl function
- cexpf function
ms.assetid: f27fd5a9-70c7-4957-a7ee-5256d19bd1da
ms.openlocfilehash: 66f7b687e8da12473abef4dbc44831e175956ac0
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555210"
---
# <a name="cexp-cexpf-cexpl"></a>cexp、cexpf、cexpl

计算复数的以 e 为底的指数。

## <a name="syntax"></a>语法

```C
_Dcomplex cexp( _Dcomplex z );
_Fcomplex cexpf( _Fcomplex z );
_Lcomplex cexpl( _Lcomplex z );

_Fcomplex cexp( _Fcomplex z );  // C++ only
_Lcomplex cexp( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>参数

*z*\
表示指数的复数。

## <a name="return-value"></a>返回值

**E**的值加上*z*的幂。

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此可以调用 **cexp** 的重载，该重载采用并返回 **_Fcomplex** 和 **_Lcomplex** 值。 在 C 程序中， **cexp** 始终采用并返回 **_Dcomplex** 值。

## <a name="requirements"></a>要求

|例程所返回的值|C 标头|C++ 标头|
|-------------|--------------|------------------|
|**cexp**、 **cexpf**、 **cexpl**|\<complex.h>|\<complex.h>|

有关兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字母函数引用](crt-alphabetical-function-reference.md)\
[cpow、cpowf、cpowl](cpow-cpowf-cpowl.md)\
[clog10、clog10f、clog10l](clog10-clog10f-clog10l.md)\
[clog、clogf、clogl](clog-clogf-clogl.md)
