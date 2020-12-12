---
description: 了解详细信息： &lt; 可选&gt;
title: （可选）&lt;&gt;
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: c1f1e6f99278abf296c361515953a931109f47ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201828"
---
# <a name="ltoptionalgt"></a>（可选）&lt;&gt;

定义容器类模板 `optional` 和多个支持模板。

## <a name="requirements"></a>要求

**标头：**\<optional>

**命名空间:** std

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|名称|描述|
|-|-|
|[operator = =](../standard-library/optional-operators.md#op_eq_eq)|测试一个对象是否等于另一个对象。|
|[operator！ =](../standard-library/optional-operators.md#op_neq)|测试一个对象是否不等于另一个对象。|
|[运算符<](../standard-library/optional-operators.md#op_lt)|测试左侧的对象是否小于右侧的对象。|
|[运算符<=](../standard-library/optional-operators.md#op_lt_eq)|测试左侧的对象是否小于或等于右侧的对象。|
|[运算符>](../standard-library/optional-operators.md#op_gt)|测试左侧的对象是否大于右侧的对象。|
|[运算符>=](../standard-library/optional-operators.md#op_lt_eq)|测试左侧的对象是否大于或等于右侧的对象。|

> [!NOTE]
> 除了关系比较以外， \<optional> 运算符还支持与 **nullopt** 和的比较 `T` 。

### <a name="functions"></a>函数

|名称|描述|
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|使对象成为可选的。|
|[swap](../standard-library/optional-functions.md#swap)|交换两个对象的包含值 `optional` 。|

### <a name="classes-and-structs"></a>类和结构

|名称|描述|
|-|-|
|hash|返回所包含的对象的哈希值。|
|[可选类](../standard-library/optional-class.md)|描述一个对象，该对象不能包含值。|
|[nullopt_t 结构](../standard-library/nullopt-t-structure.md)|描述不包含值的对象。|
|[bad_optional_access 类](../standard-library/bad-optional-access-class.md)|描述作为异常引发的对象，以报告尝试访问不存在的值。|

### <a name="objects"></a>对象

|名称|描述|
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|`nullopt_t`用于比较的实例。|

## <a name="see-also"></a>请参阅

[头文件引用](../standard-library/cpp-standard-library-header-files.md)
