---
description: 了解详细信息： allocator_newdel 类
title: allocator_newdel 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
ms.openlocfilehash: 0f514e64258ef0c1e7a4226a55a661216df9b3d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163569"
---
# <a name="allocator_newdel-class"></a>allocator_newdel 类

实现一个分配器，该分配器使用 **运算符 delete** 来释放内存块，使用 **new 运算符** 分配内存块。

## <a name="syntax"></a>语法

```cpp
template <class Type>
class allocator_newdel;
```

### <a name="parameters"></a>parameters

*类别*\
由分配器分配元素类型。

## <a name="remarks"></a>备注

[ALLOCATOR_DECL](allocators-functions.md#allocator_decl)宏将此类作为以下语句中的 *name* 参数传递：`ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="see-also"></a>请参阅

[\<allocators>](allocators-header.md)
