---
description: 了解详细信息： _clear87、_clearfp
title: _clear87、_clearfp
ms.date: 04/05/2018
api_name:
- _clearfp
- _clear87
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- clearfp
- _clearfp
- _clear87
- clear87
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
ms.openlocfilehash: c15dd66f9a6598f351a54f0269619d9768eaa152
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124951"
---
# <a name="_clear87-_clearfp"></a>_clear87、_clearfp

获取并清除浮点状态字。

## <a name="syntax"></a>语法

```C
unsigned int _clear87( void );
unsigned int _clearfp( void );
```

## <a name="return-value"></a>返回值

返回的值中的位指示调用 **_clear87** 或 **_clearfp** 之前的浮点状态。 有关 **_clear87** 返回的位的完整定义，请参阅 Float。 许多数学库函数修改了 8087/80287 状态字，结果不可预知。 如果在浮点状态字的已知状态之间执行的浮点运算更少，则从 **_clear87** 和 **_status87** 返回值变得更可靠。

## <a name="remarks"></a>备注

**_Clear87** 函数将清除浮点状态字中的异常标记，将繁忙位设置为0，并返回状态字。 浮点状态字是 8087/80287 状态字和通过 8087/80287 异常处理程序检测到的其他条件（如浮点堆栈上溢和下溢）组合而成。

**_clearfp** 是一种独立于平台的、可移植版本的 **_clear87** 例程。 它与 Intel (x86) 平台上的 **_clear87** 完全相同，并且也受 X64 和 ARM 平台的支持。 若要确保你的浮点代码可移植到 x64 和 ARM，请使用 **_clearfp**。 如果你只面向 x86 平台，则可以使用 **_clear87** 或 **_clearfp**。

使用 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md) 进行编译时，这些函数将被弃用，因为公共语言运行时仅支持默认的浮点精度。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_clear87**|\<float.h>|
|**_clearfp**|\<float.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_clear87.c
// compile with: /Od

// This program creates various floating-point
// problems, then uses _clear87 to report on these problems.
// Compile this program with Optimizations disabled (/Od).
// Otherwise the optimizer will remove the code associated with
// the unused floating-point values.
//

#include <stdio.h>
#include <float.h>

int main( void )
{
   double a = 1e-40, b;
   float x, y;

   printf( "Status: %.4x - clear\n", _clear87()  );

   // Store into y is inexact and underflows:
   y = a;
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );

   // y is denormal:
   b = y;
   printf( "Status: %.4x - denormal\n", _clear87() );
}
```

```Output
Status: 0000 - clear
Status: 0003 - inexact, underflow
Status: 80000 - denormal
```

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[_control87、_controlfp \_ _control87_2](control87-controlfp-control87-2.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
