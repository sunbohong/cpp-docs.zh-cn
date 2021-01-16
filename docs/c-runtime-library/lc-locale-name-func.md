---
description: 了解详细信息： ___lc_locale_name_func
title: ___lc_locale_name_func
ms.date: 1/14/2021
api_name:
- ___lc_locale_name_func
- _o____lc_locale_name_func
api_location:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-private-l1-1-0.dll
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___lc_locale_name_func
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
ms.openlocfilehash: 4747b64c0fc61e0f5d77eacb92c04c9f6d2e2759
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242860"
---
# <a name="___lc_locale_name_func"></a>___lc_locale_name_func

内部 CRT 函数。 检索线程的当前区域设置名称。

## <a name="syntax"></a>语法

```cpp
wchar_t** ___lc_locale_name_func(void);
```

## <a name="return-value"></a>返回值

指向包含线程的当前区域设置名称的字符串的指针。

## <a name="remarks"></a>注解

`___lc_locale_name_func` 是一个内部 CRT 函数，其他 CRT 函数可将其用于从 CRT 数据的线程本地存储中获取当前区域设置名称。 也可通过使用 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 函数或 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 函数提供此信息。

内部 CRT 函数特定于实现且会根据每个发行版本发生更改。 不建议在代码中使用它们。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`___lc_locale_name_func`|crt\src\setlocal.h|

## <a name="see-also"></a>另请参阅

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
