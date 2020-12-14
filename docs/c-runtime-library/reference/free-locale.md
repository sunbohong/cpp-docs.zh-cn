---
description: 了解详细信息： _free_locale
title: _free_locale
ms.date: 4/2/2020
api_name:
- _free_locale
- _o__free_locale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __free_locale
- free_locale
- _free_locale
helpviewer_keywords:
- __free_locale function
- free_locale function
- locales, freeing
- _free_locale function
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
ms.openlocfilehash: 441686a1ee037097c164ae60b4ccc418f0d38ac8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211266"
---
# <a name="_free_locale"></a>_free_locale

释放区域设置对象。

## <a name="syntax"></a>语法

```C
void _free_locale(
   _locale_t locale
);
```

### <a name="parameters"></a>parameters

*locale*<br/>
要释放的区域设置对象。

## <a name="remarks"></a>备注

**_Free_locale** 函数用于释放通过调用 **_get_current_locale** 或 **_create_locale** 获取的区域设置对象。

此函数的以前的名称， **__free_locale** 已弃用了两个前导下划线)  (。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|**例程所返回的值**|必需的标头|
|---------------|---------------------|
|**_free_locale**|\<locale.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[_get_current_locale](get-current-locale.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
