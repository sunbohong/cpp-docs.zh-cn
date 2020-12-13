---
description: '了解详细信息：意外的 (CRT) '
title: unexpected (CRT)
ms.date: 11/04/2016
api_name:
- unexpected
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
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 73c632c4dd5bfedbb1c3724e60786b348f77f0be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186631"
---
# <a name="unexpected-crt"></a>unexpected (CRT)

使用 **set_unexpected** 指定 **终止** 或函数。

## <a name="syntax"></a>语法

```C
void unexpected( void );
```

## <a name="remarks"></a>备注

异常 **例程不** 与 c + + 异常处理的当前实现一起使用。 默认情况下，**意外** 调用 **终止**。 可以通过以下方式更改此默认行为：编写自定义终止函数并调用 **set_unexpected** ，并将函数名称作为其参数。 **意外** 调用最后一个函数作为 **set_unexpected** 的参数。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**之外**|\<eh.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[异常处理例程](../../c-runtime-library/exception-handling-routines.md)<br/>
[中止](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[终止](terminate-crt.md)<br/>
