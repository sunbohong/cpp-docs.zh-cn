---
description: 了解详细信息： &lt; 变量 &gt; 运算符
title: '&lt;variant &gt; 运算符'
ms.date: 04/04/2019
f1_keywords:
- variant/std::operator!=
- variant/std::operator==
- variant/std::operatoroperator&gt;
- variant/std::operatoroperator&gt=;
- variant/std::operatoroperator&lt;
- variant/std::operatoroperator&lt;=
helpviewer_keywords:
- std::operator!= (variant)
- std::operator== (variant)
- std::operatoroperator&gt; (variant)
- std::operatoroperator&gt=; (variant)
- std::operatoroperator&lt; (variant)
- std::operatoroperator&lt;= (variant)
ms.openlocfilehash: 3315c73ea529ad7ade4f32be3784a43bda07ac26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312821"
---
# <a name="ltvariantgt-operators"></a>&lt;variant &gt; 运算符

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

测试运算符左侧的转发列表对象是否等于右侧的转发列表对象。

```cpp
template <class... Types>
    constexpr bool operator==(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operator"></a><a name="op_neq"></a> operator！ =

测试运算符左侧的转发列表对象是否不等于右侧的转发列表对象。

```cpp
template <class... Types>
    constexpr bool operator!=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorlt"></a><a name="op_lt"></a> 操作员&lt;

测试运算符左侧的转发列表对象是否小于右侧的转发列表对象。

```cpp
template <class... Types>
    constexpr bool operator<(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> 操作员&lt;=

测试运算符左侧的转发列表对象是否小于或等于右侧的转发列表对象。

```cpp
template <class... Types>
    constexpr bool operator<=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorgt"></a><a name="op_gt"></a> 操作员&gt;

测试运算符左侧的转发列表对象是否大于右侧的转发列表对象。

```cpp
template <class... Types> constexpr
    bool operator>(const variant<Types...>&, const variant<Types...>&);
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> 操作员&gt;=

测试运算符左侧的转发列表对象是否大于或等于右侧的转发列表对象。

```cpp
template <class... Types> constexpr
    bool operator>=(const variant<Types...>&, const variant<Types...>&);
```
