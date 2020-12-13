---
description: 了解详细信息： &lt; memory_resource &gt; 运算符
title: '&lt;memory_resource &gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- memory_resource/std::operator!=
- memory_resource/std::operator==
helpviewer_keywords:
- std::operator!= (memory_resource)
- std::operator== (memory_resource)
ms.openlocfilehash: 28c1dee4e2f022cdba14b7f71e7b9a2e40bc1162
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183836"
---
# <a name="ltmemory_resourcegt-operators"></a>&lt;memory_resource &gt; 运算符

## <a name="operator"></a><a name="op_neq"></a> operator！ =

测试运算符左侧的 memory_resource 对象是否与右侧的 memory_resource 对象不相等。

```cpp
template <class T1, class T2>
    bool operator!=(const polymorphic_allocator<T1>& a, const polymorphic_allocator<T2>& b) noexcept;
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

测试运算符左侧的 memory_resource 对象是否与右侧的 memory_resource 对象相等。

```cpp
template <class T1, class T2>
    bool operator==(const polymorphic_allocator<T1>& a, const polymorphic_allocator<T2>& b) noexcept;
```
