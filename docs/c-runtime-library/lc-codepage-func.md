---
description: 了解详细信息： ___lc_codepage_func
title: ___lc_codepage_func
ms.date: 4/2/2020
api_name:
- ___lc_codepage_func
- _o____lc_codepage_func
api_location:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
ms.openlocfilehash: b59443b8b448eb91e54548700ba7171fc0c00fd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246534"
---
# <a name="___lc_codepage_func"></a>___lc_codepage_func

内部 CRT 函数。 检索线程的当前代码页。

## <a name="syntax"></a>语法

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>返回值

线程的当前代码页。

## <a name="remarks"></a>备注

`___lc_codepage_func` 是一个内部 CRT 函数，其他 CRT 函数可将其用于从 CRT 数据的线程本地存储中获取当前代码页。 也可通过使用 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 函数提供此信息。

*代码页* 是单字节或双字节代码到单独字符的映射。 不同的代码页包含不同的特殊字符，通常会对一种语言或一组语言进行自定义。 有关代码页的详细信息，请参见 [Code Pages](../c-runtime-library/code-pages.md)。

内部 CRT 函数特定于实现且会根据每个发行版本发生更改。 不建议在代码中使用它们。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>请参阅

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
