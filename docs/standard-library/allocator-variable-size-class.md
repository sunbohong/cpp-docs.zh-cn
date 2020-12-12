---
description: 了解详细信息： allocator_variable_size 类
title: allocator_variable_size 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
ms.openlocfilehash: 9a6f9b6316daefbf436d4718a92312ceb8d55aa4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163530"
---
# <a name="allocator_variable_size-class"></a>allocator_variable_size 类

描述一个对象，该对象使用 [cache_freelist](cache-freelist-class.md)类型的缓存来管理类型 *为 type 的* 对象的存储分配和释放，其长度由 [max_variable_size](max-variable-size-class.md)管理。

## <a name="syntax"></a>语法

```cpp
template <class Type>
class allocator_variable_size;
```

### <a name="parameters"></a>parameters

*类别*\
由分配器分配元素类型。

## <a name="remarks"></a>备注

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)宏将此类作为以下语句中的 *name* 参数传递：`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="see-also"></a>请参阅

[\<allocators>](allocators-header.md)
