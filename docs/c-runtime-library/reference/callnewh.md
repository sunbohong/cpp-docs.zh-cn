---
description: 了解详细信息： _callnewh
title: _callnewh
ms.date: 4/2/2020
api_name:
- _callnewh
- _o__callnewh
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: f75028a47bbdbb6c12617a79b07a2fb8f4c5a6bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209602"
---
# <a name="_callnewh"></a>_callnewh

调用当前已安装的 *新处理程序*。

## <a name="syntax"></a>语法

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>parameters

*大小*<br/>
[新运算符](../../cpp/new-operator-cpp.md)尝试进行分配的内存量。

## <a name="return-value"></a>返回值

|值|描述|
|-----------|-----------------|
|0|失败：未安装任何新处理程序，或者无任何新处理程序处于活动状态。|
|1|成功：新的处理程序已安装并处于活动状态。 可以重试内存分配。|

## <a name="exceptions"></a>例外

如果找不到 *新处理程序*，则此函数会引发 [bad_alloc](../../standard-library/bad-alloc-class.md)。

## <a name="remarks"></a>备注

如果 [新运算符](../../cpp/new-operator-cpp.md)未能成功分配内存，则会调用 *新处理程序*。 新处理程序随后会启动一些适当的操作，如释放内存，以便成功进行后续分配。

默认情况下，此函数的全局状态的作用域限定为应用程序。 若要更改此项，请参阅 [CRT 中的全局状态](../global-state.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>请参阅

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
