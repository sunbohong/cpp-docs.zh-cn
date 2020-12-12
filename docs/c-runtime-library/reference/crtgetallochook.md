---
description: 了解详细信息： _CrtGetAllocHook
title: _CrtGetAllocHook
ms.date: 11/04/2016
api_name:
- _CrtGetAllocHook
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
- CrtGetAllocHook
- _CrtGetAllocHook
helpviewer_keywords:
- _CrtGetAllocHook function
- CrtGetAllocHook function
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
ms.openlocfilehash: 997e3a03f0c9b56fda3a0fd89daf606a652136c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319760"
---
# <a name="_crtgetallochook"></a>_CrtGetAllocHook

检索当前客户端定义的分配函数，以挂钩到 C 运行时调试内存分配进程（仅限调试版本）。

## <a name="syntax"></a>语法

```C
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );
```

## <a name="return-value"></a>返回值

返回当前定义的分配挂钩函数。

## <a name="remarks"></a>备注

**_CrtGetAllocHook** 为 C 运行时调试库内存分配进程检索当前客户端定义的应用程序挂钩函数。

有关使用其他具有挂钩功能的运行时函数和编写你自己的客户端定义挂钩函数的详细信息，请参阅[编写调试挂钩函数](/visualstudio/debugger/debug-hook-function-writing)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_CrtGetAllocHook**|\<crtdbg.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

仅限 [C 运行时库](../../c-runtime-library/crt-library-features.md)的调试版本。

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetAllocHook](crtsetallochook.md)<br/>
