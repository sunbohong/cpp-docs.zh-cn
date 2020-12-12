---
description: 了解详细信息： bidirectional_iterator_tag 结构
title: bidirectional_iterator_tag 结构
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: db8de79c0fa5f9c748d453fcba7443351dcf217d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325554"
---
# <a name="bidirectional_iterator_tag-struct"></a>bidirectional_iterator_tag 结构

一个类，该类提供 `iterator_category` 表示双向迭代器的函数的返回类型。

## <a name="syntax"></a>语法

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>备注

分类标记类用作算法选择的编译标记。 模板函数需要查找其迭代器参数的最具体的分类，以便可以在编译时使用最高效的算法。 对于每个 `Iterator` 类型的迭代器，`iterator_traits`< `Iterator`>:: **iterator_category** 必须定义为最具体的分类标记，用于描述迭代器的行为。

此类型与 **iterator** \< **Iter**> ：： **iterator_category** 在 `Iter` 描述可用作双向迭代器的对象时相同。

## <a name="example"></a>示例

有关如何使用 `bidirectional_iterator_tag` 的示例，请参阅 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)。

## <a name="requirements"></a>要求

**标头：**\<iterator>

**命名空间:** std

## <a name="see-also"></a>请参阅

[forward_iterator_tag 结构](../standard-library/forward-iterator-tag-struct.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
