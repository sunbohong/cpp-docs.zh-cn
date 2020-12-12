---
description: 了解详细信息： _findclose
title: _findclose
ms.date: 4/2/2020
api_name:
- _findclose
- _o__findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: 389a8aaf55605a1d9e3193c86ce500bf313fd631
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329197"
---
# <a name="_findclose"></a>_findclose

关闭指定的搜索句柄并释放关联资源。

## <a name="syntax"></a>语法

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>parameters

*柄*<br/>
之前对 **_findfirst** 的调用返回的搜索句柄。

## <a name="return-value"></a>返回值

如果成功， **_findclose** 将返回0。 否则，它将返回-1，并将 **errno** 设置为 **ENOENT**，指示找不到更多匹配的文件。

## <a name="remarks"></a>备注

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**_findclose**|\<io.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[系统调用](../../c-runtime-library/system-calls.md)<br/>
[文件名搜索函数](../../c-runtime-library/filename-search-functions.md)<br/>
