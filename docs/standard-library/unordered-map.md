---
title: '&lt;unordered_map&gt;'
description: C + + 标准库容器类的 API 概述 `map` 。
ms.date: 11/04/2016
f1_keywords:
- <unordered_map>
helpviewer_keywords:
- unordered_map header
ms.assetid: eb90ecb2-250a-4be1-83d2-f66b2917edde
ms.openlocfilehash: 6a25b69155f5428a7269ea35f104f30df0b61877
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042133"
---
# <a name="ltunordered_mapgt"></a>&lt;unordered_map&gt;

定义容器类模板 [unordered_map](../standard-library/unordered-map-class.md) 和 [unordered_multimap](../standard-library/unordered-multimap-class.md) 及其支持的模板。

## <a name="syntax"></a>语法

```cpp
#include <unordered_map>
```

> [!NOTE]
> \<unordered_map>该库还使用该 `#include <initializer_list>` 语句。

### <a name="classes"></a>类

|类|说明|
|-|-|
|[unordered_map 类](../standard-library/unordered-map-class.md)|存储 {key, mapped} 对的哈希表。|
|[unordered_multimap 类](../standard-library/unordered-multimap-class.md)|存储 {key, mapped} 对的哈希表。|

### <a name="functions"></a>函数

|函数|说明|
|-|-|
|[operator！ =](../standard-library/unordered-map-operators.md#op_neq)|测试位于运算符左侧的 unordered_map 对象是否与位于右侧的 unordered_map 对象不相等。|
|[operator = =](../standard-library/unordered-map-operators.md#op_eq_eq)|测试位于运算符左侧的 unordered_map 对象是否与位于右侧的 unordered_map 对象相等。|
|[swap 函数 (unordered_map)](../standard-library/unordered-map-functions.md#swap)|交换两个映射。|
|[operator！ =](../standard-library/unordered-map-operators.md#op_neq)|测试位于运算符左侧的 unordered_multimap 对象是否与位于右侧的 unordered_multimap 对象不相等。|
|[operator = =](../standard-library/unordered-map-operators.md#op_eq_eq)|测试位于运算符左侧的 unordered_multimap 对象是否与位于右侧的 unordered_multimap 对象相等。|
|[swap 函数 (unordered_map)](../standard-library/unordered-map-functions.md#swap)|交换两个多重映射。|

## <a name="see-also"></a>另请参阅

[unordered_multiset 类](../standard-library/unordered-multiset-class.md)\
[unordered_set 类](../standard-library/unordered-set-class.md)
