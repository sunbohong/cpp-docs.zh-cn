---
description: 了解详细信息： &lt; 元组&gt;
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: 7c9f55866cc723aa6f7414b6a633a3cfbebd625a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168834"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

定义了一个模板 `tuple`它的实例包括不同类型的对象。

## <a name="requirements"></a>要求

**标头：**\<tuple>

**命名空间:** std

## <a name="members"></a>成员

### <a name="classes-and-structs"></a>类和结构

|名称|描述|
|-|-|
|[元组类](../standard-library/tuple-class.md)|包装元素的固定长度序列。|
|[tuple_element 类](../standard-library/tuple-element-class-tuple.md)|包装的 `tuple` 类型的元素。|
|[tuple_size 类](../standard-library/tuple-size-class-tuple.md)|包装 `tuple` 元素计数。|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||

### <a name="objects"></a>对象

|名称|描述|
|-|-|
|[tuple_element_t](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>运算符

|名称|描述|
|-|-|
|[operator = =](../standard-library/tuple-operators.md#op_eq_eq)|比较 `tuple` 对象是否相等。|
|[operator！ =](../standard-library/tuple-operators.md#op_neq)|比较 `tuple` 对象，而不是。|
|[运算符<](../standard-library/tuple-operators.md#op_lt)|比较 `tuple` 对象，小于。|
|[运算符<=](../standard-library/tuple-operators.md#op_lt_eq)|比较 `tuple` 对象，小于或等于。|
|[运算符>](../standard-library/tuple-operators.md#op_gt)|比较 `tuple` 对象，大于。|
|[运算符>=](../standard-library/tuple-operators.md#op_gt_eq)|对象的比较 `tuple` ，大于或等于。|

### <a name="functions"></a>函数

|名称|描述|
|-|-|
|[应用](../standard-library/tuple-functions.md#apply)|使用元组调用函数。|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|构造一个引用元组。|
|[get](../standard-library/tuple-functions.md#get)|从 `tuple` 对象获取一个元素。|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|要生成的速记 `tuple` 。|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|从元素值中生成一个 `tuple`。|
|[swap](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|从元素引用中生成一个 `tuple`。|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|使用一系列类型元素构造元组对象。|

## <a name="see-also"></a>请参阅

[\<array>](../standard-library/array.md)
