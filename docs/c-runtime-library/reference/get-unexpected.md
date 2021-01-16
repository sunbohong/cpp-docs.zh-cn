---
description: 了解详细信息： _get_unexpected
title: _get_unexpected
ms.date: 1/14/2021
api_name:
- _get_unexpected
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
- __get_unexpected
- _get_unexpected
- get_unexpected
helpviewer_keywords:
- __get_unexpected function
- get_unexpected function
- _get_unexpected function
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
ms.openlocfilehash: fb23aa9eee66a4ed981e5575e5a36ad4bbb39f84
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242613"
---
# `_get_unexpected`

返回要由调用的终止例程 **`unexpected`** 。

## <a name="syntax"></a>语法

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>返回值

返回指向由注册的函数的指针 [`set_unexpected`](set-unexpected-crt.md) 。 如果尚未设置函数，则返回值可用于还原默认行为;此值可以为 **`NULL`** 。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`_get_unexpected`**|\<eh.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[异常处理例程](../../c-runtime-library/exception-handling-routines.md)<br/>
[`abort`](abort.md)<br/>
[`set_terminate`](set-terminate-crt.md)<br/>
[`terminate`](terminate-crt.md)<br/>
[`unexpected`](unexpected-crt.md)<br/>
