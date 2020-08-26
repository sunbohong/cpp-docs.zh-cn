---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: cbc93500c3fe61b2a4640008b869f3a6b71b5c6c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833304"
---
# <a name="ltlistgt"></a>&lt;list&gt;

定义容器类模板列表和多个支持模板。

## <a name="syntax"></a>语法

```cpp
#include <list>
```

> [!NOTE]
> \<list>该库还使用该 `#include <initializer_list>` 语句。

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator！ =](../standard-library/list-operators.md#op_neq)|测试运算符左侧的列表对象是否不等于右侧的列表对象。|
|[运算符<](../standard-library/list-operators.md#op_lt)|测试运算符左侧的列表对象是否小于右侧的列表对象。|
|[操作员\<=](../standard-library/list-operators.md#op_gt_eq)|测试运算符左侧的列表对象是否小于或等于右侧的列表对象。|
|[operator = =](../standard-library/list-operators.md#op_eq_eq)|测试运算符左侧的列表对象是否等于右侧的列表对象。|
|[运算符>](../standard-library/list-operators.md#op_gt)|测试运算符左侧的列表对象是否大于右侧的列表对象。|
|[运算符>=](../standard-library/list-operators.md#op_gt_eq)|测试运算符左侧的列表对象是否大于或等于右侧的列表对象。|

### <a name="functions"></a>函数

|名称|说明|
|-|-|
|[swap](../standard-library/list-functions.md#swap)|交换两个列表的元素。|

### <a name="classes"></a>类

|“属性”|说明|
|-|-|
|[list 类](../standard-library/list-class.md)|序列容器的类模板，它以线性方式维护其元素，并允许在序列内的任何位置高效插入和删除。|

## <a name="see-also"></a>另请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
