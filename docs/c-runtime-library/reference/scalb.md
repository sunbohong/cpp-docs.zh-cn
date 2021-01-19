---
description: 了解详细信息： _scalb、_scalbf
title: _scalb、_scalbf
ms.date: 1/15/2021
api_name:
- _scalb
- _scalbf
- _o__scalb
- _o__scalbf
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
- scalb
- _scalb
- _scalbf
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.openlocfilehash: da5a33bd6ed24ba0a3a58f789a9c8900910454d1
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564077"
---
# <a name="_scalb-_scalbf"></a>`_scalb`, `_scalbf`

按 2 的幂缩放自变量。

## <a name="syntax"></a>语法

```C
double _scalb(
   double x,
   long exp
);
float _scalbf(
   float x,
   long exp
); /* x64 only */
```

### <a name="parameters"></a>参数

*`x`*\
双精度浮点值。

*`exp`*\
长整数指数。

## <a name="return-value"></a>返回值

如果成功，则返回指数值。 在溢出时 (根据) 的符号 *`x`* ，将 **`_scalb`** 返回 +/- **`HUGE_VAL`** ; **`errno`** 变量设置为 **`ERANGE`** 。

有关此代码及其他返回代码的详细信息，请参阅 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>备注

**`_scalb`** 函数计算2的值 *`x`* \* <sup>*`exp`*</sup> 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`_scalb`**, **`_scalbf`**|`<float.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`ldexp`](ldexp.md)