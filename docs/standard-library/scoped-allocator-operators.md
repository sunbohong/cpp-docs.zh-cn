---
description: 了解详细信息： &lt; scoped_allocator &gt; 运算符
title: '&lt;scoped_allocator&gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 2f32a42ded9c73cbc2608f3e39f3566deee20e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197134"
---
# <a name="ltscoped_allocatorgt-operators"></a>&lt;scoped_allocator&gt; 运算符

[operator！ =](#op_neq)\
[operator = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> operator！ =

测试两个 `scoped_allocator_adaptor` 对象是否不相等。

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>parameters

*左中*\
左 `scoped_allocator_adaptor` 对象。

*然后*\
正确的 `scoped_allocator_adaptor` 对象。

### <a name="return-value"></a>返回值

`!(left == right)`

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

测试两个 `scoped_allocator_adaptor` 对象是否相等。

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>parameters

*左中*\
左 `scoped_allocator_adaptor` 对象。

*然后*\
正确的 `scoped_allocator_adaptor` 对象。

### <a name="return-value"></a>返回值

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>请参阅

[<scoped_allocator>](../standard-library/scoped-allocator.md)
