---
title: '&lt;数组&gt;'
ms.date: 11/04/2016
f1_keywords:
- <array>
helpviewer_keywords:
- array header
ms.assetid: 084147c1-e805-478e-8201-76846020f187
ms.openlocfilehash: b515578e658d658722f92e48a7ac5ab78727c465
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834942"
---
# <a name="ltarraygt"></a>&lt;数组&gt;

定义容器类模板 **数组** 和多个支持模板。

## <a name="requirements"></a>要求

**标头：**\<array>

**命名空间:** std

> [!NOTE]
> \<array>该库还使用该 `#include <initializer_list>` 语句。

## <a name="members"></a>成员

### <a name="classes"></a>类

|“属性”|说明|
|-|-|
|[array](../standard-library/array-class-stl.md)|存储元素的固定长度序列。|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|包装数组元素的类型。|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|包装数组元素的大小。|

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator = =](../standard-library/array-operators.md#op_eq_eq)|数组比较，等于|
|[operator！ =](../standard-library/array-operators.md#op_neq)|数组比较，不等于|
|[操作员\<](../standard-library/array-operators.md#op_lt)|数组比较，小于|
|[运算符>=](../standard-library/array-operators.md#op_gt_eq)|数组比较，大于或等于|
|[运算符>](../standard-library/array-operators.md#op_gt)|数组比较，大于|
|[运算符<=](../standard-library/array-operators.md#op_lt_eq)|数组的比较，小于或等于|

### <a name="functions"></a>函数

|名称|说明|
|-|-|
|[get](../standard-library/array-functions.md#get)|获取指定的数组元素。|
|[swap](../standard-library/array-functions.md#swap)|将一个数组的内容与另一个数组的内容进行交换。|

## <a name="see-also"></a>另请参阅

[\<tuple>](../standard-library/tuple.md)\
[头文件引用](../standard-library/cpp-standard-library-header-files.md)
