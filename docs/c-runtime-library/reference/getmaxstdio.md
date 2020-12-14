---
description: 了解详细信息： _getmaxstdio
title: _getmaxstdio
ms.date: 11/04/2016
api_name:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmaxstdio
- getmaxstdio
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
ms.openlocfilehash: 78c427ef9e5152708870d7ff48d0a123b7ee5213
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296545"
---
# <a name="_getmaxstdio"></a>_getmaxstdio

返回在 I/O 流级别允许同时打开的文件数。

## <a name="syntax"></a>语法

```C
int _getmaxstdio( void );
```

## <a name="return-value"></a>返回值

返回一个数字，该数字表示 **stdio.h** 级别当前允许同时打开的文件数。

## <a name="remarks"></a>备注

使用 [_setmaxstdio](setmaxstdio.md) 配置 **stdio.h** 级别允许同时打开的文件数。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_getmaxstdio**|\<stdio.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_setmaxstdio.c
// The program retrieves the maximum number
// of open files and prints the results
// to the console.

#include <stdio.h>

int main()
{
   printf( "%d\n", _getmaxstdio());

   _setmaxstdio(2048);

   printf( "%d\n", _getmaxstdio());
}
```

```Output
512
2048
```

## <a name="see-also"></a>请参阅

[流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
