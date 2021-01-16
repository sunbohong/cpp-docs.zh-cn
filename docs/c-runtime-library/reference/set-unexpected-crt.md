---
description: '了解详细信息： set_unexpected (CRT) '
title: set_unexpected (CRT)
ms.date: 1/14/2021
api_name:
- set_unexpected
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: b9918e152a5d27c853aef7769b932ee4efedeef8
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242626"
---
# <a name="set_unexpected-crt"></a>`set_unexpected` (CRT) 

安装要由调用的自己的终止函数 **`unexpected`** 。

## <a name="syntax"></a>语法

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>参数

*`unexpFunction`*\
指向一个函数的指针，您可以编写该函数来替换 **`unexpected`** 函数。

## <a name="return-value"></a>返回值

返回指向注册的上一个终止函数的指针， **`_set_unexpected`** 以便稍后可以还原以前的函数。 如果以前未设置函数，则返回值可用于还原默认行为;此值可以为 **`NULL`** 。

## <a name="remarks"></a>注解

**`set_unexpected`** 函数将 *unexpFunction* 安装为由调用的函数 **`unexpected`** 。 **`unexpected`** 不在当前 c + + 异常处理实现中使用。 该 **`unexpected_function`** 类型在 EH 中定义。H 作为指向用户定义的意外函数的指针， *unexpFunction* 返回 **`void`** 。 自定义 *unexpFunction* 函数不应返回到其调用方。

```cpp
typedef void ( *unexpected_function )( );
```

默认情况下，会 **`unexpected`** 调用 **`terminate`** 。 可以通过以下方式更改此默认行为：编写自己的终止函数并调用 **`set_unexpected`** 作为参数的函数名称。 **`unexpected`** 调用作为的参数提供的最后一个函数 **`set_unexpected`** 。

不同于通过调用安装的自定义终止功能 **`set_terminate`** ，可以从中引发异常 **`unexpFunction`** 。

在多线程环境中，单独为每个线程维护意外函数。 每个新线程都需要安装它自己的意外函数。 因此，每个线程都负责它自己的意外处理。

在当前的 c + + 异常处理实现中 **`unexpected`** ， **`terminate`** 默认情况下调用，而不是由异常处理运行时库调用。 调用（而不是 term'inate）没有特别的优势 **`unexpected`** 。 

**`set_unexpected`** 对于所有动态链接的 dll 或 exe，都有一个处理程序; 即使调用 **`set_unexpected`** 处理程序可以被另一个 DLL 或 exe 替换为其他 DLL 或 exe，也是如此。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`set_unexpected`**|`<eh.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[异常处理例程](../../c-runtime-library/exception-handling-routines.md)\
[`abort`](abort.md)\
[`_get_unexpected`](get-unexpected.md)\
[`set_terminate`](set-terminate-crt.md)\
[`terminate`](terminate-crt.md)\
[`unexpected`](unexpected-crt.md)\
