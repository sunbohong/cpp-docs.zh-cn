---
title: '&lt;allocators&gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 2d2f928ab3773ed8e0b0afdc0113db2ef5b2a3dd
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561213"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 运算符

这些是在分配器中定义的全局模板运算符函数 &lt; &gt; 。 有关类成员运算符函数的详细说明，请参阅类文档。

|||
|-|-|
|[operator！ =](#op_neq)|[operator = =](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a> operator！ =

测试指定类的分配器对象之间是否不相等。

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>参数

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

### <a name="parameters"></a>参数

*左中*\
要测试是否相等的其中一个分配器对象。

*然后*\
要测试是否相等的其中一个分配器对象。

### <a name="return-value"></a>返回值

**`true`** 如果分配器对象相等，则为; **`false`** 如果分配器对象不相等，则为。

### <a name="remarks"></a>备注

此模板运算符返回 `left.equals(right)`。

## <a name="see-also"></a>另请参阅

[\<allocators>](allocators-header.md)
