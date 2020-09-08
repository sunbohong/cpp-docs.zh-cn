---
title: erf、erff、erfl、erfc、erfcf、erfcl
description: 适用于 erf、erff、erfl、erfc、erfcf 和 erfcl 的 API 参考;计算错误函数或值的互补错误函数的。
ms.date: 9/1/2020
api_name:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
- _o_erf
- _o_erfc
- _o_erfcf
- _o_erfcl
- _o_erff
- _o_erfl
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
- erfl
- erf
- erff
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: ef83275515c66341798395bbfc2bb5b088e6cfb7
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555639"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf、erff、erfl、erfc、erfcf、erfcl

计算某个值的误差函数或补余误差函数。

## <a name="syntax"></a>语法

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
#define erf(X) // Requires C11 or higher
#define erfc(X) // Requires C11 or higher
```

### <a name="parameters"></a>参数

*x-blade*\
浮点值。

## <a name="return-value"></a>返回值

**Erf**函数返回*x*的高斯错误函数。 **Erfc**函数返回*x*的互补高斯错误函数。

## <a name="remarks"></a>备注

**Erf**函数计算*x*的高斯错误函数，该函数定义为：

![x 的错误函数](media/crt_erf_formula.PNG "x 的错误函数")

互补高斯错误函数定义为 1-erf (x) 。 **Erf**函数返回的值范围为-1.0 到1.0。 无错误返回。 **Erfc**函数返回0到2范围内的值。 如果 *x* 对于 **erfc**太大，则将 **errno** 变量设置为 **ERANGE**。

由于 c + + 允许重载，因此你可以调用采用并返回和类型的 **erf** 和 **erfc** 的重载 **`float`** **`long double`** 。 在 C 程序中，除非使用 \<tgmath.h> 宏调用此函数，否则， **erf** 和 **erfc** 始终采用并返回 **`double`** 。

如果使用 \<tgmath.h> `erf()` 宏，则参数的类型将决定选择哪个版本的函数。 有关详细信息，请参阅 [类型-泛型数学](../../c-runtime-library/tgmath.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**erf**、 **erff**、 **erfl**、 **erfc**、 **erfcf**、 **erfcl**|\<math.h>|
|**erf** 宏 | \<tgmath.h> |

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
