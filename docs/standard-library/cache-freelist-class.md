---
description: 了解详细信息： cache_freelist 类
title: cache_freelist 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: 9d5b3da272cff39b0c9d7d69df2c744d6952cd03
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325377"
---
# <a name="cache_freelist-class"></a>cache_freelist 类

定义分配和释放单个大小内存块的[块分配器](../standard-library/allocators-header.md)。

## <a name="syntax"></a>语法

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>parameters

*Sz*\
数组中要分配的元素数目。

*数量*\
表示释放列表的最大大小的 max 类。 其可以是 [max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md) 或 [max_variable_size](../standard-library/max-variable-size-class.md)。

## <a name="remarks"></a>备注

Cache_freelist 类模板维护一个大小为 *Sz* 的内存块的免费列表。 当可用列表已满时，它将使用 **运算符 delete** 来释放内存块。 当可用列表为空时，它将使用 **operator new** 来分配新的内存块。 可用列表的最大大小由 *最* 大参数中传递的类 max 类确定。

每个内存块都包含 *Sz* 字节的可用内存和 **运算符 new** 和 **运算符 delete** 需要的数据。

### <a name="constructors"></a>构造函数

|构造函数|说明|
|-|-|
|[cache_freelist](#cache_freelist)|构造 `cache_freelist` 类型的对象。|

### <a name="member-functions"></a>成员函数

|成员函数|说明|
|-|-|
|[分配](#allocate)|分配内存块。|
|[写意](#deallocate)|从指定位置开始从存储中释放指定数量的的对象。|

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="cache_freelistallocate"></a><a name="allocate"></a> cache_freelist：： allocate

分配内存块。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>parameters

*计*\
数组中要分配的元素数目。

### <a name="return-value"></a>返回值

指向已分配对象的指针。

### <a name="remarks"></a>备注

## <a name="cache_freelistcache_freelist"></a><a name="cache_freelist"></a> cache_freelist：： cache_freelist

构造 `cache_freelist` 类型的对象。

```cpp
cache_freelist();
```

### <a name="remarks"></a>备注

## <a name="cache_freelistdeallocate"></a><a name="deallocate"></a> cache_freelist：:d eallocate

从指定位置开始从存储中释放指定数量的的对象。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>parameters

*ptr*\
指向要从存储中释放的第一个对象的指针。

*计*\
要从存储中释放的对象数量。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[\<allocators>](../standard-library/allocators-header.md)
