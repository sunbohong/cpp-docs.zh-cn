---
description: 了解有关以下内容的详细信息：分配器 &lt; void &gt; 类
title: allocator&lt;void&gt; 类
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
ms.openlocfilehash: a6468c35f4660736cd297ffd7ae3d0738bbf0756
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163504"
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; 类

类模板分配器到类型的专用化 **`void`** ，用于定义在此上下文中有意义的类型。

## <a name="syntax"></a>语法

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>备注

类为类型显式专用化类模板 [分配](allocator-class.md) 器 **`void`** 。 其构造函数和赋值运算符的行为与类模板的行为相同，但它只定义以下类型：

- [const_pointer](allocator-class.md#const_pointer)。

- [指针](allocator-class.md#pointer)。

- [value_type](allocator-class.md#value_type)。

- 重新[绑定](allocator-class.md#rebind)，嵌套类模板。
