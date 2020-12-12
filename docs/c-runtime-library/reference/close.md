---
description: 了解详细信息： _close
title: _close
ms.date: 4/2/2020
api_name:
- _close
- _o__close
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: d65d65cea5d379cad11e45e63efc725ee056ea91
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260730"
---
# <a name="_close"></a>_close

关闭文件。

## <a name="syntax"></a>语法

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>parameters

*fd*<br/>
引用打开的文件的文件说明符。

## <a name="return-value"></a>返回值

如果文件已成功关闭， **_close** 将返回0。 返回值-1 表示错误。

## <a name="remarks"></a>备注

**_Close** 函数将关闭与 *fd* 关联的文件。

文件描述符和基础 OS 文件句柄已关闭。 因此，如果最初使用 Win32 函数 **CreateFile** 打开该文件并使用 **_open_osfhandle** 将其转换为文件描述符，则无需调用 **CloseHandle** 。

此函数验证其参数。 如果 *fd* 是错误的文件描述符，则调用无效参数处理程序，如 [参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则函数将返回-1，并且 **errno** 设置为 **ebadf (**。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|可选标头|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅 [_open](open-wopen.md) 示例。

## <a name="see-also"></a>请参阅

[低级别 i/o](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_dup，_dup2](dup-dup2.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_unlink、_wunlink](unlink-wunlink.md)<br/>
