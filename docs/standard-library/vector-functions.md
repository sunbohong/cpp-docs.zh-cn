---
description: 了解有关以下内容的详细信息： &lt; 向量 &gt; 函数
title: '&lt;vector&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: c59e2626a2062be90d2cb8201b058d5ee148ef55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187879"
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 函数

## <a name="swap"></a><a name="swap"></a> 购

交换两个向量的元素。

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>parameters

*然后*\
提供要交换的元素的向量，或其元素将要与向量 *左侧* 的元素进行交换的向量。

*左中*\
其元素将与向量 *右* 的元素进行交换的向量。

### <a name="remarks"></a>备注

模板函数是一个专用于容器类向量的算法，用于执行成员函数 `left` 。 [vector：： swap](../standard-library/vector-class.md) *( 向右*) 。 这些是由编译器进行的函数模板部分排序的实例。 模板函数以此种方式重载时，模板与函数调用的匹配并不唯一，随后编译器会选择此模板函数的最专用化版本。 算法类中的模板函数的通用版本 " **`template`** \< **class T**> **void** " ( **t&**， **t&**) ，在赋值时，它是一种慢速操作。 每个容器中的专用化版本速度快很多，因为专用化版本可适用于容器类的内部表示形式。

### <a name="example"></a>示例

有关使用 `swap` 的模板版本的示例，请参阅成员函数 [vector::swap](../standard-library/vector-class.md) 的代码示例。
