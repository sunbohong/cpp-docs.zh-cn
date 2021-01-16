---
description: 了解详细信息： __pctype_func
title: __pctype_func
ms.date: 1/14/2021
api_name:
- __pctype_func
- _o___pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- api-ms-win-crt-private-l1-1-0.dll
- api-ms-win-crt-locale-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: 492f4a4c6ff5a23c05c15267d7ac00f72bc6eb94
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242951"
---
# <a name="__pctype_func"></a>__pctype_func

检索指向字符分类信息数组的指针。

## <a name="syntax"></a>语法

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>返回值

指向字符分类信息数组的指针。

## <a name="remarks"></a>注解

字符分类表中的信息仅供内部使用，由对类型的字符进行分类的各种函数使用 **`char`** 。 有关详细信息，请参阅 [_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md) 中的 `Remarks` 部分。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>另请参阅

[_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
