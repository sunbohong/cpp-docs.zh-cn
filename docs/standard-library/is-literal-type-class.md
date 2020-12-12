---
description: 了解详细信息： is_literal_type 类
title: is_literal_type 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 97cb609c5a42bed0be205b1b51ff901d3e366bb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323681"
---
# <a name="is_literal_type-class"></a>is_literal_type 类

测试某一类型是否可用作 **`constexpr`** 变量，或可由函数构造、使用或从函数返回 **`constexpr`** 。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *T* 是 *文本类型*，则类型谓词的实例为 true; 否则为 false。 文本类型可以是 **`void`** 、标量类型、引用类型、文本类型的数组或文本类类型。 文本类类型是一个具有普通析构函数的类类型，要么是聚合类型，要么至少具有一个非移动、非复制 **`constexpr`** 构造函数，并且其所有基类和非静态数据成员都是非易失文本类型。 尽管文本的类型始终是文本类型，但文本类型的概念包含编译器可以在编译时计算的任何内容 **`constexpr`** 。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)
