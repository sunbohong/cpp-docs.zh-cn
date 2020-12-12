---
description: 了解详细信息： const_mem_fun1_t 类
title: const_mem_fun1_t 类
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 998826bbd78745913caf76ad6b152aac490956fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233651"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t 类

一种适配器类， **`const`** 在使用指针参数进行初始化时，此类允许使用单个自变量的成员函数作为二元函数对象调用。 在 c + + 11 中已弃用，在 c + + 17 中删除。

## <a name="syntax"></a>语法

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>parameters

*member_ptr*\
一个指针，指向要转换为函数对象的 `Type` 类成员函数。

*左中*\
**`const`** 在其上调用 *member_ptr* 成员函数的对象。

*然后*\
要提供给 *member_ptr* 的参数。

## <a name="return-value"></a>返回值

一个自适应二元函数。

## <a name="remarks"></a>备注

类模板 `Type` 在私有成员对象中存储 member_ptr 的副本，该副本必须是指向类的成员函数的指针。 它将其成员函数定义 `operator()` 为返回 `(left->member_ptr)(right) const` 。

## <a name="example"></a>示例

很少直接使用 `const_mem_fun1_t` 的构造函数。 `mem_fn` 用于改编成员函数。 有关如何使用成员函数适配器的示例，请参阅 [mem_fn](../standard-library/functional-functions.md#mem_fn) 。
