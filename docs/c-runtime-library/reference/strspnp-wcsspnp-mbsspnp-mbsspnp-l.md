---
description: 了解详细信息： _strspnp、_wcsspnp、_mbsspnp、_mbsspnp_l
title: _strspnp、_wcsspnp、_mbsspnp、_mbsspnp_l
ms.date: 4/2/2020
api_name:
- _mbsspnp
- _wcsspnp
- _mbsspnp_l
- _strspnp
- _o__mbsspnp
- _o__mbsspnp_l
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
- _tcsspnp
- _mbsspnp
- strspnp
- _ftcsspnp
- _mbsspnp_l
- wcsspnp
- mbsspnp_l
- _wcsspnp
- _strspnp
- mbsspnp
helpviewer_keywords:
- _strspnp function
- _wcsspnp function
- _mbsspnp_l function
- strspnp function
- mbsspnp function
- wcsspnp function
- _mbsspnp function
- mbsspnp_l function
- _tcsspnp function
- tcsspnp function
ms.assetid: 1ce18100-2edd-4c3b-af8b-53f204d80233
ms.openlocfilehash: 7b043e96d99644e4534dd2de3202575e2e7cf833
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198721"
---
# <a name="_strspnp-_wcsspnp-_mbsspnp-_mbsspnp_l"></a>_strspnp、_wcsspnp、_mbsspnp、_mbsspnp_l

返回指向给定字符串（不在另一个给定字符串）中的第一个字符的指针。

> [!IMPORTANT]
> 不能在 Windows 运行时中执行的应用程序中使用 **_mbsspnp** 和 **_mbsspnp_l** 。 有关详细信息，请参阅[通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。

## <a name="syntax"></a>语法

```C
char *_strspnp(
   const char *str,
   const char *charset
);
wchar_t *_wcsspnp(
   const unsigned wchar_t *str,
   const unsigned wchar_t *charset
);
unsigned char *_mbsspnp(
   const unsigned char *str,
   const unsigned char *charset
);
unsigned char *_mbsspnp_l(
   const unsigned char *str,
   const unsigned char *charset,
   _locale_t locale
);
```

### <a name="parameters"></a>parameters

*str*<br/>
要搜索的 null 终止的字符串。

*charset*<br/>
null 终止的字符集。

*locale*<br/>
要使用的区域设置。

## <a name="return-value"></a>返回值

**_strspnp**、 **_wcsspnp** 和 **_mbsspnp** 返回指向 *str* 中的第一个字符的指针，该字符不属于 *字符集* 中的字符集。 如果 *str* 包含 *字符集* 中的所有字符，则这些函数将返回 **NULL** 。 对于这些例程，都不会保留返回值来指示错误。

## <a name="remarks"></a>备注

**_Mbsspnp** 函数返回一个指向多字节字符的指针，该字符是 *str* 中的第一个字符，该字符不属于 *字符集* 中的字符集。 **_mbsspnp** 根据当前使用的 [多字节代码页](../../c-runtime-library/code-pages.md) 识别多字节字符序列。 搜索不包括结尾的 null 字符。

如果 *str* 或 *字符集* 为空指针，此函数将调用无效参数处理程序，如 [参数验证](../../c-runtime-library/parameter-validation.md)中所述。 如果允许执行继续，则该函数将返回 **NULL** ，并将 **Errno** 设置为 **EINVAL**。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|Tchar.h 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsspnp**|**_strspnp**|**_mbsspnp**|**_wcsspnp**|

**_strspnp** 和 **_wcsspnp** 是 **_mbsspnp** 的单字节字符和宽字符版本。 与 **_mbsspnp** 的 **_strspnp** 和 **_wcsspnp** 的行为相同; 否则为。它们仅为此映射提供，不应用于任何其他原因。 有关详细信息，请参阅[使用一般文本映射](../../c-runtime-library/using-generic-text-mappings.md)和[一般文本映射](../../c-runtime-library/generic-text-mappings.md)。

**_mbsspnp_l** 相同，只不过它使用传入的区域设置参数。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_mbsspnp**|\<mbstring.h>|
|**_strspnp**|\<tchar.h>|
|**_wcsspnp**|\<tchar.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_mbsspnp.c
#include <mbstring.h>
#include <stdio.h>

int main( void ) {
   const unsigned char string1[] = "cabbage";
   const unsigned char string2[] = "c";
   unsigned char *ptr = 0;
   ptr = _mbsspnp( string1, string2 );
   printf( "%s\n", ptr);
}
```

### <a name="output"></a>输出

```Output
abbage
```

## <a name="see-also"></a>请参阅

[字符串操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[区域设置](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character 序列的解释](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strncat_s、_strncat_s_l、wcsncat_s、_wcsncat_s_l、_mbsncat_s、_mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
