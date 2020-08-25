---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: de88feb691d0ec1bc9bf9b9dc2bc40cbc31a1cfe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831042"
---
# <a name="ltmemory_resourcegt"></a>&lt;memory_resource&gt;

定义容器类模板 memory_resource 及其支持的模板。

## <a name="syntax"></a>语法

```cpp
#include <memory_resource>
```

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator！ =](../standard-library/memory-resource-operators.md#op_neq)|测试运算符左侧的 memory_resource 对象是否与右侧的 memory_resource 对象不相等。|
|[operator = =](../standard-library/memory-resource-operators.md#op_eq_eq)|测试运算符左侧的 memory_resource 对象是否与右侧的 memory_resource 对象相等。|

### <a name="specialized-template-functions"></a>专用化模板函数

|名称|说明|
|-|-|
|[polymorphic_allocator](../standard-library/memory-resource-functions.md#poly_alloc)||

### <a name="functions"></a>函数

|名称|说明|
|-|-|
|[get_default_resource](../standard-library/memory-resource-functions.md#get_default)||
|[new_delete_resource](../standard-library/memory-resource-functions.md#new_delete)||
|[null_memory_resource](../standard-library/memory-resource-functions.md#null_memory)||
|[set_default_resource](../standard-library/memory-resource-functions.md#set_default)||

### <a name="classes-and-structs"></a>类和结构

|名称|说明|
|-|-|
|[memory_resource 类](../standard-library/memory-resource-class.md)||
|[monotonic_buffer_resource 类](../standard-library/monotonic-buffer-resource-class.md)||
|[pool_options 结构](../standard-library/pool-options-structure.md)||
|[synchronized_pool_resource 类](../standard-library/synchronized-pool-resource-class.md)||
|[unsynchronized_pool_resource 类](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>另请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
