---
description: 了解详细信息： type_index 类
title: type_index 类
ms.date: 11/04/2016
f1_keywords:
- typeindex/std::type_index
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
ms.openlocfilehash: 4e9156420811d2712a5b9331d0ece0e7847103e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142683"
---
# <a name="type_index-class"></a>type_index 类

`type_index` 类将指针包装到 [type_info 类](../cpp/type-info-class.md)，以便通过这些对象辅助编写索引。

类 type_index {public： type_index (const type_info& tinfo) ; const char * name ( # A9 const; size_t hash_code ( # A11 const; bool 运算符 = = (const type_info& right) const; bool 运算符！ = (const type_info& right) const; bool 运算符< (const type_info& right) const; bool 运算符 \<=(const type_info& right) const;
   bool operator> (const type_info& right) const; bool 运算符>= (const type_info& right) const;};

构造函数将 `ptr` 初始化为 `&tinfo`。

`name` 返回 `ptr->name()`。

`hash_code` 返回 `ptr->hash_code().`

`operator==` 返回 `*ptr == right.ptr`。

`operator!=` 返回 `!(*this == right)`。

`operator<` 返回 `*ptr->before(*right.ptr)`。

`operator<=` 返回 `!(right < *this).`

`operator>` 返回 `right < *this`。

`operator>=` 返回 `!(*this < right)`。

## <a name="see-also"></a>请参阅

[运行时类型信息](../cpp/run-time-type-information.md)\
[\<typeindex>](../standard-library/typeindex.md)
