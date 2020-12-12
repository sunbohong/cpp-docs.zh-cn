---
description: 了解详细信息： is_trivially_assignable 类
title: is_trivially_assignable 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_assignable
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
ms.openlocfilehash: fbbf14b83dff4bea9ed50eddf93512899f6d9fb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118545"
---
# <a name="is_trivially_assignable-class"></a>is_trivially_assignable 类

测试 `From` 类型的值是否能够普通赋予 `To` 类型

## <a name="syntax"></a>语法

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>parameters

*自*\
接收赋值的对象的类型。

*从*\
提供值的对象的类型。

## <a name="remarks"></a>备注

表达式 `declval<To>() = declval<From>()` 必须格式正确，且编译器必须已知其不需要任何重要操作。 `From`和 `To` 必须是完整类型、 **`void`** 或未知绑定的数组。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
