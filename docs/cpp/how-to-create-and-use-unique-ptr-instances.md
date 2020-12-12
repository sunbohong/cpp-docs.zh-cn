---
description: 了解有关详细信息，请参阅如何：创建和使用 unique_ptr 实例
title: 如何：创建和使用 unique_ptr 实例
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: a53b3a9704c62803b50c9bde2c7db70c190a8008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268660"
---
# <a name="how-to-create-and-use-unique_ptr-instances"></a>如何：创建和使用 unique_ptr 实例

[Unique_ptr](../standard-library/unique-ptr-class.md)不共享其指针。 不能将其复制到另一个，而是 `unique_ptr` 通过值传递给函数，也不能在需要进行复制的任何 c + + 标准库算法中使用。 只能移动 `unique_ptr`。 这意味着，内存资源所有权将转移到另一 `unique_ptr`，并且原始 `unique_ptr` 不再拥有此资源。 我们建议你将对象限制为由一个所有者所有，因为多个所有权会使程序逻辑变得复杂。 因此，当你需要一个智能指针用于纯 c + + 对象时，请使用 `unique_ptr` ，当构造时， `unique_ptr` 请使用 [make_unique](../standard-library/memory-functions.md#make_unique) helper 函数。

下图演示了两个 `unique_ptr` 实例之间的所有权转换。

![移动唯一&#95;ptr 的所有权](media/unique_ptr.png "移动唯一&#95;ptr 的所有权")

`unique_ptr` 是在 `<memory>` c + + 标准库的标头中定义的。 它与原始指针一样高效，并且可在 c + + 标准库容器中使用。 将实例添加 `unique_ptr` 到 c + + 标准库容器是有效的，因为的移动构造函数 `unique_ptr` 无需进行复制操作。

## <a name="example-1"></a>示例 1

以下示例演示如何创建 `unique_ptr` 实例并在函数之间传递这些实例。

[!code-cpp[stl_smart_pointers#210](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

这些示例说明了 `unique_ptr` 的基本特征：可移动，但不可复制。 “移动”将所有权转移到新 `unique_ptr` 并重置旧 `unique_ptr`。

## <a name="example-2"></a>示例 2

以下示例演示如何创建 `unique_ptr` 实例并在向量中使用这些实例。

[!code-cpp[stl_smart_pointers#211](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

在 range for 循环中，注意 `unique_ptr` 通过引用来传递。 如果你尝试通过此处的值传递，由于删除了 `unique_ptr` 复制构造函数，编译器将引发错误。

## <a name="example-3"></a>示例 3

以下示例演示如何初始化类成员 `unique_ptr`。

[!code-cpp[stl_smart_pointers#212](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example-4"></a>示例 4

可以使用 [make_unique](../standard-library/memory-functions.md#make_unique) 为 `unique_ptr` 数组创建，但不能使用 `make_unique` 来初始化数组元素。

[!code-cpp[stl_smart_pointers#213](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

有关更多示例，请参阅 [make_unique](../standard-library/memory-functions.md#make_unique)。

## <a name="see-also"></a>请参阅

[智能指针（现代 C++）](smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)
