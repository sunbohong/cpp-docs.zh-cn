---
title: '`_mbsnbcat_s`, `_mbsnbcat_s_l`'
description: Microsoft Visual C++ `_mbsnbcat_s` 和函数的 API 说明 `_mbsnbcat_s_l`
ms.date: 12/2/2020
api_name:
- _mbsnbcat_s_l
- _mbsnbcat_s
- _o__mbsnbcat_s
- _o__mbsnbcat_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: c7198d806d8ebe077b423ff2135b5bdcf66ffac6
ms.sourcegitcommit: 9c45483572db4470fe5db5a7b596d5770303098c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "96523109"
---
# <a name="_mbsnbcat_s-_mbsnbcat_s_l"></a>`_mbsnbcat_s`, `_mbsnbcat_s_l`

最多追加到另一个多字节字符字符串的前 **n** 个字节字符串中的多字节字符串。 这些是具有安全增强功能的版本[ `_mbsnbcat` ， `_mbsnbcat_l` ](mbsnbcat-mbsnbcat-l.md)如[CRT 中的安全功能](../../c-runtime-library/security-features-in-the-crt.md)中所述。

> [!IMPORTANT]
> 此 API 不能用于在 Windows 运行时中执行的应用程序。 有关详细信息，请参阅[通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。

## <a name="syntax"></a>语法

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>参数

*`dest`*\
以 null 终止的多字节字符目标字符串。

*`sizeInBytes`*\
缓冲区的大小 *`dest`* （以字节为单位）。

*`src`*\
以 null 终止的多字节字符源字符串。

*`count`*\
*`src`* 要追加到的字节数 *`dest`* 。

*`locale`*\
要使用的区域设置。

## <a name="return-value"></a>返回值

如果成功，则为零；否则为错误代码。

### <a name="error-conditions"></a>错误条件

|**`dest`**|*`sizeInBytes`*|*`src`*|返回值|
|------------|-------------------|-----------|------------------|
|**`NULL`**|any|any|**`EINVAL`**|
|任意|<= 0|any|**`EINVAL`**|
|任意|any|**`NULL`**|**`EINVAL`**|

如果出现任何一个错误状态，该函数生成无效参数错误，如[参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果处理错误，则函数返回 **`EINVAL`** 并将 **errno** 设置为 **`EINVAL`** 。

## <a name="remarks"></a>备注

**`_mbsnbcat_s`** 函数最多追加到的 *`dest`* 第一个 *`count`* 字节 *`src`* 。 如果中紧跟在 null 字符之前的字节 *`dest`* 是前导字节，则它将被的初始字节覆盖 *`src`* 。 否则，的初始字节会 *`src`* 覆盖的终止 null 字符 *`dest`* 。 如果在追加字节之前出现 null 字节，则将 *`src`* *`count`* 从中 **`_mbsnbcat_s`** 追加 *`src`* 到 null 字符的所有字节。 如果 *`count`* 大于的长度 *`src`* ， *`src`* 则使用的长度代替 *`count`* 。 生成的字符串由 null 字符终止。 如果复制出现在重叠的字符串之间，则该行为不确定。

输出值受区域设置的类别设置的影响 **`LC_CTYPE`** ; 有关详细信息 [_wsetlocale，](setlocale-wsetlocale.md) 请参阅 setlocale。 这些函数的版本相同，不同之处在于不包含后缀的函数 **`_l`** 使用当前区域设置，而具有后缀的那些函数 **`_l`** 使用传入的区域设置参数。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。

在 c + + 中，模板重载简化了这些函数的使用。 重载可以自动推导出缓冲区长度，从而无需指定大小自变量，并且它们可以自动使用更新、更安全的函数替换较旧、不安全的函数。 有关详细信息，请参阅[安全模板重载](../../c-runtime-library/secure-template-overloads.md)。

这些函数的调试库版本首先用0xFE 填充缓冲区。 若要禁用此行为，请使用 [`_CrtSetDebugFillThreshold`](crtsetdebugfillthreshold.md) 。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|`Tchar.h` 例程|`_UNICODE` 和 `_MBCS` 未定义|`_MBCS` 明确|`_UNICODE` 明确|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**`_tcsncat_s`**|[strncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|**`_mbsnbcat_s`**|[wcsncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|
|**`_tcsncat_s_l`**|**`_strncat_s_l`**|**`_mbsnbcat_s_l`**|**`_wcsncat_s_l`**|

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`_mbsnbcat_s`**|\<mbstring.h>|
|**`_mbsnbcat_s_l`**|\<mbstring.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[字符串操作](../../c-runtime-library/string-manipulation-crt.md)\
[`_mbsnbcmp`, `_mbsnbcmp_l`](mbsnbcmp-mbsnbcmp-l.md)\
[`_strncnt`, `_wcsncnt`, `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, `_mbsnccnt_l`](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)\
[`_mbsnbcpy`, `_mbsnbcpy_l`](mbsnbcpy-mbsnbcpy-l.md)\
[`_mbsnbcpy_s`, `_mbsnbcpy_s_l`](mbsnbcpy-s-mbsnbcpy-s-l.md)\
[`_mbsnbset`, `_mbsnbset_l`](mbsnbset-mbsnbset-l.md)\
[`strncat`, `_strncat_l`, `wcsncat`, `_wcsncat_l`, `_mbsncat`, `_mbsncat_l`](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)\
[`strncat_s`, `_strncat_s_l`, `wcsncat_s`, `_wcsncat_s_l`, `_mbsncat_s`, `_mbsncat_s_l`](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)
