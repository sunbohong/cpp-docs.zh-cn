---
description: 了解详细信息： &lt; 分配器 &gt; 运算符
title: '&lt;allocators&gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: a0289ca7b76aaddb2e6c8ed20a58a61d1be40998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163465"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 运算符

这些是在分配器中定义的全局模板运算符函数 &lt; &gt; 。 有关类成员运算符函数的详细说明，请参阅类文档。

[operator！ =](#op_neq)\
[operator = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> operator！ =

测试指定类的分配器对象之间是否不相等。

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>parameters

*左中*\
要测试是否不相等的其中一个分配器对象。

*然后*\
要测试是否不相等的其中一个分配器对象。

### <a name="return-value"></a>返回值

**`true`** 如果分配器对象不相等，则为; 否则为。 **`false`** 如果分配器对象相等，则为。

### <a name="remarks"></a>备注

模板运算符返回 `!(left == right)`。

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

测试指定类的分配器对象之间是否相等。

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>parameters

*左中*\
要测试是否相等的其中一个分配器对象。

*然后*\
要测试是否相等的其中一个分配器对象。

### <a name="return-value"></a>返回值

**`true`** 如果分配器对象相等，则为; **`false`** 如果分配器对象不相等，则为。

### <a name="remarks"></a>备注

此模板运算符返回 `left.equals(right)`。

## <a name="see-also"></a>请参阅

[\<allocators>](allocators-header.md)
