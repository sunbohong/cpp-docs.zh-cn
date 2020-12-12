---
description: 了解详细信息： allocator_suballoc 类
title: allocator_suballoc 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
helpviewer_keywords:
- allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
ms.openlocfilehash: 7e542b4b8f419f1ac219c63b113aced7e0bd7cda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163582"
---
# <a name="allocator_suballoc-class"></a>allocator_suballoc 类

描述一个对象，该对象使用 [cache_suballoc](cache-suballoc-class.md)类型的缓存管理类型 *为 type 的* 对象的存储分配和释放。

## <a name="syntax"></a>语法

```cpp
template <class Type>
class allocator_suballoc;
```

### <a name="parameters"></a>parameters

*类别*\
由分配器分配元素类型。

## <a name="remarks"></a>备注

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)宏将此类作为以下语句中的 *name* 参数传递：`ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="see-also"></a>请参阅

[\<allocators>](allocators-header.md)
