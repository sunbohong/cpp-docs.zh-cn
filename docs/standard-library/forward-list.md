---
title: '&lt;forward_list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <forward_list>
helpviewer_keywords:
- <forward_list>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: 6966d8513d78b6bbe3831709f52daa04c67b4572
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835735"
---
# <a name="ltforward_listgt"></a>&lt;forward_list&gt;

定义容器类模板 forward_list 和多个支持模板。

## <a name="requirements"></a>要求

**标头：**\<forward_list>

**命名空间:** std

> [!NOTE]
> \<forward_list>该库还使用该 `#include <initializer_list>` 语句。

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator = =](../standard-library/forward-list-operators.md#op_eq_eq)|测试运算符左侧的转发列表对象是否等于右侧的转发列表对象。|
|[operator！ =](../standard-library/forward-list-operators.md#op_neq)|测试运算符左侧的转发列表对象是否不等于右侧的转发列表对象。|
|[运算符<](../standard-library/forward-list-operators.md#op_lt)|测试运算符左侧的转发列表对象是否小于右侧的转发列表对象。|
|[运算符<=](../standard-library/forward-list-operators.md#op_lt_eq)|测试运算符左侧的转发列表对象是否小于或等于右侧的转发列表对象。|
|[运算符>](../standard-library/forward-list-operators.md#op_gt)|测试运算符左侧的转发列表对象是否大于右侧的转发列表对象。|
|[运算符>=](../standard-library/forward-list-operators.md#op_lt_eq)|测试运算符左侧的转发列表对象是否大于或等于右侧的转发列表对象。|

### <a name="functions"></a>函数

|名称|说明|
|-|-|
|[swap](../standard-library/forward-list-functions.md#swap)|交换两个转发列表的元素。|

### <a name="classes"></a>类

|“属性”|说明|
|-|-|
|[forward_list](../standard-library/forward-list-class.md)|描述用于控制变长元素序列的对象。 序列存储为元素的单向链接列表，其中每个节点都包含 `Type` 类型的成员。|

## <a name="see-also"></a>另请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)
