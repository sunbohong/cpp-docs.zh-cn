---
description: 了解详细信息： isblank、iswblank、_isblank_l、_iswblank_l
title: isblank、iswblank、_isblank_l、_iswblank_l
ms.date: 4/2/2020
api_name:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
- _o_isblank
- _o_iswblank
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: a2731468cda3a2d3bf059133f116b22fa2b019f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321108"
---
# <a name="isblank-iswblank-_isblank_l-_iswblank_l"></a>isblank、iswblank、_isblank_l、_iswblank_l

确定整数是否表示空格字符。

## <a name="syntax"></a>语法

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>parameters

*c*<br/>
要测试的整数。

*locale*<br/>
要使用的区域设置。

## <a name="return-value"></a>返回值

如果 *c* 是空格或水平制表符的特定表示形式，或者是用于在文本行中分隔单词的特定于区域设置的字符集中，则每个例程将返回非零值。 如果 *c* 是空格字符 (0x20) 或水平制表符 (0x09) ，则 **isblank** 将返回一个非零值。 **Isblank** 函数的测试条件的结果取决于区域设置的 **LC_CTYPE** 类别设置;有关详细信息，请参阅 [setlocale、_wsetlocale](setlocale-wsetlocale.md)。 没有 **_l** 后缀的这些函数的版本对与区域设置相关的行为使用当前区域设置;具有 **_l** 后缀的版本是相同的，只不过它们使用传入的区域设置。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。

如果 *c* 是对应于标准空格或水平制表符的宽字符，则 **iswblank** 将返回一个非零值。

如果 *c* 不是 EOF 或介于0到0xff （含0和0xff），则 **isblank** 和 **_isblank_l** 的行为是不确定的。 当使用调试 CRT 库并且 *c* 不是这些值之一时，函数将引发断言。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="remarks"></a>备注

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**isblank**|\<ctype.h>|
|**iswblank**|\<ctype.h> 或 \<wchar.h>|
|**_isblank_l**|\<ctype.h>|
|**_iswblank_l**|\<ctype.h> 或 \<wchar.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[字符分类](../../c-runtime-library/character-classification.md)<br/>
[区域设置](../../c-runtime-library/locale.md)<br/>
[为，isw 例程](../../c-runtime-library/is-isw-routines.md)<br/>
