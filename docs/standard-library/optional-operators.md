---
description: 了解详细信息： &lt; 可选 &gt; 运算符
title: '&lt;可选 &gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- optional/std::operator!=
- optional/std::operator==
- optional/std::operatoroperator&gt;
- optional/std::operatoroperator&gt=;
- optional/std::operatoroperator&lt;
- optional/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (optional)
- std::operator== (optional)
- std::operatoroperator&gt; (optional)
- std::operatoroperator&gt=; (optional)
- std::operatoroperator&lt; (optional)
- std::operatoroperator&lt;= (optional)
ms.openlocfilehash: 3c61f62ff87ab285dfeb5b26f1d22de86ef50fee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201854"
---
# <a name="ltoptionalgt-operators"></a>&lt;可选 &gt; 运算符

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

测试运算符左侧的 `optional` 对象是否等于右侧的 `optional` 对象。

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>parameters

*左中*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

*然后*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

## <a name="operator"></a><a name="op_neq"></a> operator！ =

测试运算符左侧的 `optional` 对象是否不等于右侧的 `optional` 对象。

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>parameters

*左中*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

*然后*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

### <a name="remarks"></a>备注

此模板函数返回 `!(left == right)`。

## <a name="operatorlt"></a><a name="op_lt"></a> 操作员&lt;

测试运算符左侧的 `optional` 对象是否小于右侧的 `optional` 对象。

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>parameters

*左中*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

*然后*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的列表小于但不等于运算符右侧的列表，则为; 否则为。否则为 **`false`** 。

## <a name="operatorlt"></a><a name="op_lt_eq"></a> 操作员&lt;=

测试运算符左侧的 `optional` 对象是否小于或等于右侧的 `optional` 对象。

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>parameters

*左中*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

*然后*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的列表小于或等于运算符右侧的列表，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>备注

此模板函数返回 `!(right < left)`。

## <a name="operatorgt"></a><a name="op_gt"></a> 操作员&gt;

测试运算符左侧的 `optional` 对象是否大于右侧的 `optional` 对象。

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>parameters

*左中*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

*然后*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的列表大于运算符右侧的列表，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>备注

此模板函数返回 `right < left`。

## <a name="operatorgt"></a><a name="op_gt_eq"></a> 操作员&gt;=

测试运算符左侧的 `optional` 对象是否大于或等于右侧的 `optional` 对象。

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>parameters

*左中*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

*然后*\
类型为 `optional` 、或的对象 `nullopt_t` `T` 。

### <a name="return-value"></a>返回值

**`true`** 如果 `optional` 运算符左侧的大于或等于 `optional` 运算符右侧的，则为; 否则为 **`false`** 。

### <a name="remarks"></a>备注

此模板函数返回 `!(left < right)`。
