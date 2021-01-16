---
description: 了解详细信息： wctype
title: wctype
ms.date: 1/14/2021
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
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctype
helpviewer_keywords:
- wctype function
- wide characters
ms.openlocfilehash: d0afd2bd163af967b11d0df58c84b62521ca6c2a
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242920"
---
# `wctype`

确定宽字符代码的分类规则。

## <a name="syntax"></a>语法

```C
wctype_t wctype(
   const char * property
);
```

### <a name="parameters"></a>参数

*`property`*\
属性字符串。

## <a name="return-value"></a>返回值

如果 **`LC_CTYPE`** 当前区域设置的类别未定义其名称与属性字符串匹配的分类规则 *`property`* ，则函数将返回零。 否则，它将返回一个适合用作对的后续调用的第二个参数的非零值 [`towctrans`](towctrans.md) 。

## <a name="remarks"></a>注解

此函数将确定宽字符代码的分类规则。 以下调用对在所有区域设置中具有相同的行为（但实现可定义其他分类规则，甚至在“C”区域设置中）：

|函数|与以下项相同|
|--------------|-------------|
|`iswalnum(c)`|`iswctype(c, wctype( "alnum" ))`|
|`iswalpha(c)`|`iswctype(c, wctype( "alpha" ))`|
|`iswcntrl(c)`|`iswctype(c, wctype( "cntrl" ))`|
|`iswdigit(c)`|`iswctype(c, wctype( "digit" ))`|
|`iswgraph(c)`|`iswctype(c, wctype( "graph" ))`|
|`iswlower(c)`|`iswctype(c, wctype( "lower" ))`|
|`iswprint(c)`|`iswctype(c, wctype( "print" ))`|
|`iswpunct(c)`|`iswctype(c, wctype( "punct" ))`|
|`iswspace(c)`|`iswctype(c, wctype( "space" ))`|
|`iswupper(c)`|`iswctype(c, wctype( "upper" ))`|
|`iswxdigit(c)`|`iswctype(c, wctype( "xdigit" ))`|

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`wctype`|`<wctype.h>`|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另请参阅

[数据转换](../../c-runtime-library/data-conversion.md)\
[`setlocale`, `_wsetlocale`](setlocale-wsetlocale.md)
