---
description: 了解详细信息： ___setlc_active_func、___unguarded_readlc_active_add_func
title: ___setlc_active_func、___unguarded_readlc_active_add_func
ms.date: 11/04/2016
api_name:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
api_location:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
ms.openlocfilehash: 85273b52102e9cca2e42ba4401da60b1d292560c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277076"
---
# <a name="___setlc_active_func-___unguarded_readlc_active_add_func"></a>___setlc_active_func、___unguarded_readlc_active_add_func

已过时。 CRT 仅导出这些内部函数以保留二进制兼容性。

## <a name="syntax"></a>语法

```cpp
int ___setlc_active_func(void);
int * ___unguarded_readlc_active_add_func(void);
```

## <a name="return-value"></a>返回值

返回的值不重要。

## <a name="remarks"></a>备注

尽管内部 CRT 函数 `___setlc_active_func` 和 `___unguarded_readlc_active_add_func` 已过时且不再使用，但是 CRT 库还会导出它们以保留二进制兼容性。 `___setlc_active_func` 的原始用途是返回对 `setlocale` 函数的当前活动的调用数。 `___unguarded_readlc_active_add_func` 的原始用途是返回引用区域设置而不会锁定区域设置的函数数。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|无|

## <a name="see-also"></a>请参阅

[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
