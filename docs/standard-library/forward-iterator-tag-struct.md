---
description: 了解详细信息： forward_iterator_tag 结构
title: forward_iterator_tag 结构
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 9b8b5ea7ff4e7d68c14c892d4ba6ef96f275b7da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324290"
---
# <a name="forward_iterator_tag-struct"></a>forward_iterator_tag 结构

一种为代表向前迭代器的 **iterator_category** 函数提供返回类型的类。

## <a name="syntax"></a>语法

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>备注

分类标记类用作算法选择的编译标记。 模板函数需要查找其迭代器参数的最具体的分类，以便可以在编译时使用最高效的算法。 对于每个 `Iterator` 类型的迭代器，`iterator_traits`< `Iterator`> **::iterator_category** 必须定义为最特定的类别标记，用于描述迭代器的行为。

 \< **Iter**> 当 **Iter** 描述可用作向前迭代器的对象时，该类型与 iterator **：： iterator_category** 相同。

## <a name="example"></a>示例

有关如何使用 **iterator_tag** 的示例，请参阅 [iterator_traits](../standard-library/iterator-traits-struct.md) 或 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)。

## <a name="requirements"></a>要求

**标头：**\<iterator>

**命名空间:** std

## <a name="see-also"></a>请参阅

[input_iterator_tag 结构](../standard-library/input-iterator-tag-struct.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
