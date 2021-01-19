---
title: fabs、fabsf、fabsl
description: 适用于 fabs、fabsf 和 fabsl 的 API 参考;它计算浮点值的绝对值。
ms.date: 1/15/2021
api_name:
- fabsf
- fabs
- fabsl
- _o_fabs
- _o_fabsf
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.openlocfilehash: 453965b846dff9affb3fa6dce99ea8b6189a5d6c
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563921"
---
# <a name="fabs-fabsf-fabsl"></a>`fabs`, `fabsf`, `fabsl`

计算浮点自变量的绝对值。

## <a name="syntax"></a>语法

```C
double fabs(
   double x
);
float fabs(
   float x
); // C++ only
long double fabs(
   long double x
); // C++ only
float fabsf(
   float x
);
long double fabsl(
   long double x
);

#define fabs(X) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*`x`*\
浮点值。

## <a name="return-value"></a>返回值

**`fabs`** 函数返回参数 *x* 的绝对值。 无错误返回。

|输入|SEH 异常|`Matherr` 异常|
|-----------|-------------------|-----------------------|
|± `QNAN`,`IND`|无|`_DOMAIN`|

## <a name="remarks"></a>备注

C + + 允许重载，因此， **`fabs`** 如果包含标头，则可以调用的重载 `<cmath>` 。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`fabs`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `fabs()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的 C 标头|必需的 C++ 标头|
|--------------|-----------------------|---------------------------|
|**`fabs`**, **`fabsf`**, **`fabsl`**|`<math.h>`|`<cmath>` 或 `<math.h>`|
|**`fabs`** 宏定义 | `<tgmath.h>` ||

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅的示例 [`abs`](abs-labs-llabs-abs64.md) 。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`abs, labs, llabs, _abs64`](abs-labs-llabs-abs64.md)\
[`_cabs`](cabs.md)
