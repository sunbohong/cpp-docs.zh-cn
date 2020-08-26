---
title: '&lt;set&gt;'
ms.date: 11/04/2016
f1_keywords:
- <set>
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
ms.openlocfilehash: 4ac5c0bbf94c4d17389efb424d2e12b84717c4a9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846220"
---
# <a name="ltsetgt"></a>&lt;set&gt;

定义容器类模板集和多集及其支持的模板。

## <a name="requirements"></a>要求

**标头：**\<set>

**命名空间:** std

> [!NOTE]
> \<set>该库还使用该 `#include <initializer_list>` 语句。

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|Set 版本|Multiset 版本|说明|
|-|-|-|
|[operator！ = (集) ](../standard-library/set-operators.md#op_neq)|[operator！ = (多集) ](../standard-library/set-operators.md#op_neq)|测试运算符左侧的 set 或 multiset 对象是否不等于右侧的 set 或 multiset 对象。|
|[运算符< (集) ](../standard-library/set-operators.md#op_lt)|[运算符< (多重集) ](../standard-library/set-operators.md#op_lt_multiset)|测试运算符左侧的 set 或 multiset 对象是否小于右侧的 set 或 multiset 对象。|
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator \< = (多重集) ](../standard-library/set-operators.md#op_lt_eq_multiset)|测试运算符左侧的 set 或 multiset 对象是否小于或等于右侧的 set 或 multiset 对象。|
|[operator = = (集) ](../standard-library/set-operators.md#op_eq_eq)|[operator = = (多集) ](../standard-library/set-operators.md#op_eq_eq_multiset)|测试运算符左侧的 set 或 multiset 对象是否等于右侧的 set 或 multiset 对象。|
|[运算符> (集) ](../standard-library/set-operators.md#op_gt)|[运算符> (多重集) ](../standard-library/set-operators.md#op_gt_multiset)|测试运算符左侧的 set 或 multiset 对象是否大于右侧的 set 或 multiset 对象。|
|[运算符>= (集) ](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|测试运算符左侧的 set 或 multiset 对象是否大于或等于右侧的 set 或 multiset 对象。|

### <a name="specialized-template-functions"></a>专用化模板函数

|Set 版本|Multiset 版本|说明|
|-|-|-|
|[swap](../standard-library/set-functions.md#swap)|[交换 (多重集) ](../standard-library/set-functions.md#swap_multiset)|交换两个集或多个集的元素。|

### <a name="classes"></a>类

|“属性”|说明|
|-|-|
|[set 类](../standard-library/set-class.md)|用于存储和检索集合中的数据，此集合中包含的元素值是唯一的，并且用作数据自动排序所依据的关键字值。|
|[多重集类](../standard-library/multiset-class.md)|用于存储和检索集合中的数据，此集合中包含的元素值不必是唯一的，并且可用作数据自动排序所依据的关键字值。|

## <a name="see-also"></a>另请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
