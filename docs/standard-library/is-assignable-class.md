---
description: 了解详细信息： is_assignable 类
title: is_assignable 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: 4165e69de99b7fdb8ae1524d1755e738c846d7c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323855"
---
# <a name="is_assignable-class"></a>is_assignable 类

测试 `From` 类型的值是否可以分配给 `To` 类型。

## <a name="syntax"></a>语法

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>parameters

*自*\
接收赋值的对象的类型。

*从*\
提供值的对象的类型。

## <a name="remarks"></a>备注

未计算的表达式 `declval<To>() = declval<From>()` 必须具有正确格式。 `From`和 `To` 必须是完整类型、 **`void`** 或未知绑定的数组。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
