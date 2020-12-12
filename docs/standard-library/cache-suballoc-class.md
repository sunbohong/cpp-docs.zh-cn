---
description: 了解详细信息： cache_suballoc 类
title: cache_suballoc 类
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 9df13155101a77d327c8bdee9da1fe03bfa00366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325364"
---
# <a name="cache_suballoc-class"></a>cache_suballoc 类

定义分配和释放单个大小内存块的[块分配器](../standard-library/allocators-header.md)。

## <a name="syntax"></a>语法

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>parameters

*Sz*\
数组中要分配的元素数目。

## <a name="remarks"></a>备注

当可用列表为空时，cache_suballoc 类模板会将已释放的内存块存储在自由列表中，其长度 `freelist<sizeof(Type), max_unbounded>` 不受限制 、使用和 suballocates 内存块。

每个区块都包含 `Sz * Nelts` 可用内存和 **运算符 new** 和 **运算符 delete** 需要的数据。 不会释放已分配的区块。

### <a name="constructors"></a>构造函数

|构造函数|说明|
|-|-|
|[cache_suballoc](#cache_suballoc)|构造 `cache_suballoc` 类型的对象。|

### <a name="member-functions"></a>成员函数

|成员函数|说明|
|-|-|
|[分配](#allocate)|分配内存块。|
|[写意](#deallocate)|从指定位置开始从存储中释放指定数量的的对象。|

## <a name="requirements"></a>要求

**标头：**\<allocators>

**命名空间：** stdext

## <a name="cache_suballocallocate"></a><a name="allocate"></a> cache_suballoc：： allocate

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

## <a name="cache_suballoccache_suballoc"></a><a name="cache_suballoc"></a> cache_suballoc：： cache_suballoc

构造 `cache_suballoc` 类型的对象。

```cpp
cache_suballoc();
```

### <a name="remarks"></a>备注

## <a name="cache_suballocdeallocate"></a><a name="deallocate"></a> cache_suballoc：:d eallocate

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
