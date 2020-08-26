---
title: '&lt;queue&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: a41d34b45264472a5c8c88ca0619e78444dd8aec
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832589"
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

定义类模板 priority_queue 和队列和多个支持模板。

## <a name="requirements"></a>要求

**标头：**\<queue>

**命名空间:** std

> [!NOTE]
> \<queue>该库还使用该 `#include <initializer_list>` 语句。

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator！ =](../standard-library/queue-operators.md#op_neq)|测试运算符左侧和右侧的 queue 对象是否不相等。|
|[运算符<](../standard-library/queue-operators.md#op_lt)|测试运算符左侧的 queue 对象是否小于右侧的 queue 对象。|
|[操作员\<=](../standard-library/queue-operators.md#op_gt_eq)|测试运算符左侧的 queue 对象是否小于或等于右侧的 queue 对象。|
|[operator = =](../standard-library/queue-operators.md#op_eq_eq)|测试运算符左侧和右侧的 queue 对象是否相等。|
|[运算符>](../standard-library/queue-operators.md#op_gt)|测试运算符左侧的 queue 对象是否大于右侧的 queue 对象。|
|[运算符>=](../standard-library/queue-operators.md#op_gt_eq)|测试运算符左侧的 queue 对象是否大于或等于右侧的 queue 对象。|

### <a name="classes"></a>类

|“属性”|说明|
|-|-|
|[queue 类](../standard-library/queue-class.md)|一个模板容器适配器类，它提供功能的限制，限制一些基本容器类型的前端和后端元素的访问权限。|
|[priority_queue 类](../standard-library/priority-queue-class.md)|一个模板容器适配器类，它提供功能的限制，限制一些基本容器类型顶端元素的访问权限，并且该类通常为最大类。|

## <a name="see-also"></a>另请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
