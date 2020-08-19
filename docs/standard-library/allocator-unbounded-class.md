---
title: allocator_unbounded 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
ms.openlocfilehash: d9d82dd29ab86654020e13b39a8c9588ee0732e8
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561539"
---
# <a name="allocator_unbounded-class"></a>allocator_unbounded 类

描述一个对象，该对象使用[cache_freelist](cache-freelist-class.md)类型的缓存来管理类型*为 type 的*对象的存储分配和释放，其长度由[max_unbounded](max-unbounded-class.md)管理。

## <a name="syntax"></a>语法

```cpp
template <class Type>
class allocator_unbounded;
```

### <a name="parameters"></a>参数

*类别*\
由分配器分配元素类型。

## <a name="remarks"></a>注解

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)宏将此类作为以下语句中的*name*参数传递：`ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="see-also"></a>另请参阅

[\<allocators>](allocators-header.md)
