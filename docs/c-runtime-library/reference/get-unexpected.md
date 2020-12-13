---
description: 了解详细信息： _get_unexpected
title: _get_unexpected
ms.date: 11/04/2016
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
ms.openlocfilehash: 9c8f21815aa465e1325ef0519ba21abb1e506db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338942"
---
# <a name="_get_unexpected"></a>_get_unexpected

返回 **意外** 调用的终止例程。

## <a name="syntax"></a>语法

```C
unexpected_function _get_unexpected( void );
```

## <a name="return-value"></a>返回值

返回指向 [set_unexpected](set-unexpected-crt.md) 注册的函数的指针。 如果尚未设置函数，则返回值可用于还原默认行为;此值可以为 **NULL**。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_get_unexpected**|\<eh.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[异常处理例程](../../c-runtime-library/exception-handling-routines.md)<br/>
[中止](abort.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[终止](terminate-crt.md)<br/>
[之外](unexpected-crt.md)<br/>
