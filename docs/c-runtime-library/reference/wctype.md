---
description: 了解详细信息： wctype
title: wctype
ms.date: 11/04/2016
api_name:
- wctype
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
ms.openlocfilehash: 0791d4f048dfa5d6804db14d577b1370ffbf8754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254191"
---
# <a name="wctype"></a>wctype

确定宽字符代码的分类规则。

## <a name="syntax"></a>语法

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>parameters

*property*<br/>
属性字符串。

## <a name="return-value"></a>返回值

如果当前区域设置的 **LC_CTYPE** 类别未定义其名称与属性字符串 *属性* 匹配的分类规则，则函数将返回零。 否则，它将返回一个适合用作对 [towctrans](towctrans.md) 的后续调用的第二个参数的非零值。

## <a name="remarks"></a>备注

此函数将确定宽字符代码的分类规则。 以下调用对在所有区域设置中具有相同的行为（但实现可定义其他分类规则，甚至在“C”区域设置中）：

|函数|与以下项相同|
|--------------|-------------|
|iswalnum (c) |iswctype (c，wctype ( "alnum" ) ) |
|iswalpha (c) |iswctype (c，wctype ( "alpha" ) ) |
|iswcntrl (c) |iswctype (c，wctype ( "cntrl" ) ) |
|iswdigit (c) |iswctype (c，wctype ( "数字" ) ) |
|iswgraph (c) |iswctype (c，wctype ( "graph" ) ) |
|iswlower (c) |iswctype (c，wctype ( "lower" ) ) |
|iswprint (c) |iswctype (c，wctype ( "print" ) ) |
|iswpunct (c) |iswctype (c，wctype ( "punct" ) ) |
|iswspace (c) |iswctype (c，wctype ( "space" ) ) |
|iswupper (c) |iswctype (c，wctype ( "upper" ) ) |
|iswxdigit (c) |iswctype (c，wctype ( "xdigit" ) ) |

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**wctype**|\<wctype.h>|

有关其他兼容性信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[数据转换](../../c-runtime-library/data-conversion.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
