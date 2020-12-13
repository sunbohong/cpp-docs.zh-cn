---
description: 了解详细信息： _onexit、_onexit_m
title: _onexit、_onexit_m
ms.date: 11/04/2016
api_name:
- _onexit
- _onexit_m
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _onexit
- onexit_m
- onexit
- _onexit_m
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
ms.openlocfilehash: 0b79c521b04a4cb1597dda7c7ed2a19ae2dcf905
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151692"
---
# <a name="_onexit-_onexit_m"></a>_onexit、_onexit_m

注册在退出时要调用的例程。

## <a name="syntax"></a>语法

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>parameters

*函数*<br/>
指向在退出时要调用的函数的指针。

## <a name="return-value"></a>返回值

如果成功，则 **_onexit** 返回指向函数的指针; 如果没有空间存储函数指针，则返回 **NULL** 。

## <a name="remarks"></a>备注

**_Onexit** 函数传递函数 (*函数* 的地址，) 在程序正常终止时调用该函数。 对 **_onexit** 的后续调用将创建一个函数寄存器，这些函数将在 LIFO (后进先出) 顺序执行。 传递给 **_onexit** 的函数不能采用参数。

如果从 DLL 中调用 **_onexit** ，则使用 **_onexit** 注册的例程将在使用 DLL_PROCESS_DETACH 调用 **DllMain** 后，在 dll 的卸载上运行。

**_onexit** 是 Microsoft 扩展。 若要获得 ANSI 可移植性，请使用 [atexit](atexit.md)。 函数的 **_onexit_m** 版本适用于混合模式使用。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>输出

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>请参阅

[进程和环境控制](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>
