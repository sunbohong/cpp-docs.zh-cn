---
title: '&lt;map&gt;'
ms.date: 11/04/2016
f1_keywords:
- <map>
helpviewer_keywords:
- map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
ms.openlocfilehash: 9a58160c573fac7d4ad170f589c04c75b456299a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846428"
---
# <a name="ltmapgt"></a>&lt;map&gt;

定义容器类模板 map 和多重映射及其支持的模板。

## <a name="requirements"></a>要求

**标头：**\<map>

**命名空间:** std

> [!NOTE]
> \<map>该库还使用该 `#include <initializer_list>` 语句。

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|Map 版本|Multimap 版本|说明|
|-----------------|----------------------|-----------------|
|[operator！ = (map) ](../standard-library/map-operators.md#op_neq)|[operator！ = (多重映射) ](../standard-library/map-operators.md#op_neq)|测试运算符左侧和右侧的 map 或 multimap 对象是否不相等。|
|[运算符< (映射) ](../standard-library/map-operators.md#op_eq_eq)|[操作员< (多重映射) ](../standard-library/map-operators.md#op_eq_eq)|测试运算符左侧的 map 或 multimap 对象是否小于右侧的 map 或 multimap 对象。|
|[运算符<= (映射) ](../standard-library/map-operators.md#op_lt)|[operator \< = (多重映射) ](../standard-library/map-operators.md#op_lt)|测试运算符左侧的 map 或 multimap 对象是否小于或等于右侧的 map 或 multimap 对象。|
|[operator = = (map) ](../standard-library/map-operators.md#op_eq_eq)|[operator = = (多重映射) ](../standard-library/map-operators.md#op_eq_eq_multimap)|测试运算符左侧和右侧的 map 或 multimap 对象是否相等。|
|[运算符> (映射) ](../standard-library/map-operators.md#op_gt)|[操作员> (多重映射) ](../standard-library/map-operators.md#op_gt_multimap)|测试运算符左侧的 map 或 multimap 对象是否大于右侧的 map 或 multimap 对象。|
|[operator>= (map)](../standard-library/map-operators.md#op_gt_eq)|[运算符>= (多重映射) ](../standard-library/map-operators.md#op_gt_eq_multimap)|测试运算符左侧的 map 或 multimap 对象是否大于或等于右侧的 map 或 multimap 对象。|

### <a name="specialized-template-functions"></a>专用化模板函数

|Map 版本|Multimap 版本|说明|
|-----------------|----------------------|-----------------|
|[交换 (地图) ](../standard-library/map-functions.md#swap)|[交换 (多重映射) ](../standard-library/map-functions.md#swap_multimap)|交换两个 map 或 multimap 的元素。|

### <a name="classes"></a>类

|“属性”|说明|
|-|-|
|[value_compare 类](../standard-library/value-compare-class-map.md)|提供一个函数对象，它能通过比较其键的值来比较映射的元素，以确定其在映射中的相对顺序。|
|[map 类](../standard-library/map-class.md)|用于存储和检索集合中的数据，此集合中每个元素都有用于自动排列数据的唯一键。|
|[多重映射类](../standard-library/multimap-class.md)|用于存储和检索集合中的数据，此集合中每个元素都有一个用于自动排列数据的键，且这些键不需要具有唯一值。|

## <a name="see-also"></a>另请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
