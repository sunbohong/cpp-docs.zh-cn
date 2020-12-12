---
description: 了解详细信息： &lt; 新建 &gt; typedef
title: '&lt;new&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 0c8e73f10b8429d2c55805c017dded98843af9f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338156"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

## <a name="hardware_constructive_interference_size"></a><a name="hardware_constructive_interference_size"></a> hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>备注

此数字是通过并发线程使用时态位置访问的两个对象所占用的最大连续内存大小。 它应至少为 `alignof(max_align_t)` 。

### <a name="example"></a>示例

```cpp
struct together {
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a><a name="hardware_destructive_interference_size"></a> hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>备注

此数字是两个并发访问的对象之间的最小建议偏移量，以避免因实现引入的争用而导致的额外性能下降。 它应至少为 `alignof(max_align_t)` 。

### <a name="example"></a>示例

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a><a name="new_handler"></a> new_handler

该类型指向适合用作新处理程序的函数。

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>备注

此类型的处理程序函数由 **new 运算符** 调用，或 `operator new[]` 在无法满足额外存储的请求时调用。

### <a name="example"></a>示例

有关将 `new_handler` 用作返回值的示例，请参阅 [set_new_handler](../standard-library/new-functions.md#set_new_handler)。
