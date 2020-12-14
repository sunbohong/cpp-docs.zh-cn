---
description: 了解详细信息： _cexit、_c_exit
title: _cexit、_c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: e901e7d7e37c8702efaae8b3b70e98a400f48ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275095"
---
# <a name="_cexit-_c_exit"></a>_cexit、_c_exit

执行清理操作并返回，而不终止进程。

## <a name="syntax"></a>语法

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>备注

**_Cexit** 函数在后进先出 (后进先出) order，通过 **atexit** 和 **_onexit** 注册的函数。 然后 **_cexit** 刷新所有的 i/o 缓冲区并在返回前关闭所有打开的流。 **_c_exit** 与 **_exit** 相同，但是返回到调用进程，但不处理 **atexit** 或 **_onexit** 或刷新流缓冲区。 下表显示了 **exit**、 **_exit**、 **_cexit** 和 **_c_exit** 的行为。

|函数|行为|
|--------------|--------------|
|**exit**|执行完整的 C 库终止过程，终止进程，并使用提供的状态代码退出。|
|**_exit**|执行快速的 C 库终止过程，终止进程，并使用提供的状态代码退出。|
|**_cexit**|执行完整的 C 库终止过程并返回给调用方，但不中止进程。|
|**_c_exit**|执行快速的 C 库终止过程并返回给调用方，但不中止进程。|

调用 **_cexit** 或 **_c_exit** 函数时，不会调用在调用时存在的任何临时或自动对象的析构函数。 自动对象是在对象未声明为静态的函数中进行定义的对象。 临时对象是由编译器创建的对象。 若要在调用 **_cexit** 或 **_c_exit** 之前销毁自动对象，请显式调用该对象的析构函数，如下所示：

```cpp
myObject.myClass::~myClass( );
```

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[进程和环境控制](../../c-runtime-library/process-and-environment-control.md)<br/>
[中止](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec，_wexec 函数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn，_wspawn 函数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
