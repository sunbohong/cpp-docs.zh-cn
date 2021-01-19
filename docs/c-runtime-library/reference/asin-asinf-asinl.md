---
title: asin、asinf、asinl
description: 适用于 asin、asinf 和 asinl 的 API 参考;计算浮点值的反正弦值。
ms.date: 1/15/2021
api_name:
- asinf
- asinl
- asin
- _o_asin
- _o_asinf
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.openlocfilehash: 04b68e9b5933d763cecbdc06af3e34a5b7c01223
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564038"
---
# <a name="asin-asinf-asinl"></a>`asin`, `asinf`, `asinl`

计算反正弦值。

## <a name="syntax"></a>语法

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
#define asin(X) // Requires C11 or higher

float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>参数

*`x`*\
要计算反正弦值的值。

## <a name="return-value"></a>返回值

**`asin`** 函数返回反正弦函数的反正弦值 (， *`x`* 范围为-π/2 到π/2 弧度的反正弦函数) 。

默认情况下，如果 *`x`* 小于-1 或大于1，则 **`asin`** 返回无限期的。

|输入|SEH 异常|Matherr 异常|
|-----------|-------------------|-----------------------|
|± ∞|**`INVALID`**|**`_DOMAIN`**|
|± **`QNAN`**, **`IND`**|无|**`_DOMAIN`**|
|&#124;x&#124;>1|**`INVALID`**|**`_DOMAIN`**|

## <a name="remarks"></a>备注

由于 c + + 允许重载，因此你可以调用 **`asin`** 具有 **`float`** 和值的的重载 **`long double`** 。 在 C 程序中，除非使用 `<tgmath.h>` 宏调用此函数，否则 **`asin`** 始终采用并返回 **`double`** 。

如果使用 `<tgmath.h>` `asin()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头 (C)|必需的标头 (C++)|
|-------------|---------------------|-|
|**`asin`**, **`asinf`**, **`asinl`**|`<math.h>`|`<cmath>` 或 `<math.h>`|
|**`asin()`** 宏定义 | `<tgmath.h>` ||

## <a name="example"></a>示例

有关详细信息，请参阅[ `acos` 、 `acosf` 、 `acosl` ](acos-acosf-acosl.md)。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)\
[`acos`, `acosf`, `acosl`](acos-acosf-acosl.md)\
[`atan`, `atanf`, `atanl`, `atan2`, `atan2f`, `atan2l`](atan-atanf-atanl-atan2-atan2f-atan2l.md)\
[`cos`, `cosf`, `cosl`](cos-cosf-cosl.md)\
[`_matherr`](matherr.md)\
[`sin`, `sinf`, `sinl`](sin-sinf-sinl.md)\
[`tan`, `tanf`, `tanl`](tan-tanf-tanl.md)