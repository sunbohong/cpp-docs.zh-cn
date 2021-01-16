---
description: '了解详细信息：意外的 (CRT) '
title: unexpected (CRT)
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- unexpected
helpviewer_keywords:
- unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
ms.openlocfilehash: 098d686e7c33d17020990b1db168d95c327d5112
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242899"
---
# <a name="unexpected-crt"></a>`unexpected` (CRT) 

调用 **`terminate`** 或使用指定的函数 **`set_unexpected`** 。

## <a name="syntax"></a>语法

```C
void unexpected( void );
```

## <a name="remarks"></a>备注

**`unexpected`** 例程不与 c + + 异常处理的当前实现一起使用。 **`unexpected`****`terminate`** 默认情况下调用。 您可以通过编写自定义终止函数来更改此默认行为。 调用 **`set_unexpected`** ，并将函数名称作为其参数。 **`unexpected`** 调用传递到的最后一个函数 **`set_unexpected`** 。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`unexpected`**|`<eh.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[异常处理例程](../../c-runtime-library/exception-handling-routines.md)<br/>
[中止](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[终止](terminate-crt.md)<br/>
