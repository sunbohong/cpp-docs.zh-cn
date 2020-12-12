---
description: 了解详细信息： &lt; 分配器 &gt; 宏
title: '&lt;allocators&gt; 宏'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
helpviewer_keywords:
- std::ALLOCATOR_DECL [C++]
- std::CACHE_CHUNKLIST [C++]
- std::CACHE_FREELIST [C++]
- std::CACHE_SUBALLOC [C++]
- std::SYNC_DEFAULT [C++]
ms.openlocfilehash: c4866495787cbf502997ca08a06e57ed667f4e9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163517"
---
# <a name="ltallocatorsgt-macros"></a>&lt;allocators&gt; 宏

:::row:::
   :::column span="":::
      [`ALLOCATOR_DECL`](#allocator_decl)\
      [`CACHE_CHUNKLIST`](#cache_chunklist)
   :::column-end:::
   :::column span="":::
      [`CACHE_FREELIST`](#cache_freelist)
   :::column-end:::
   :::column span="":::
      [`CACHE_SUBALLOC`](#cache_suballoc)
   :::column-end:::
   :::column span="":::
      [`SYNC_DEFAULT`](#sync_default)
   :::column-end:::
:::row-end:::

## <a name="allocator_decl"></a><a name="allocator_decl"></a> ALLOCATOR_DECL

生成分配器类模板。

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>备注

该宏将生成一个模板定义 `template <class Type> class name {.....}` 和一个特殊化， `template <> class name<void> {.....}` 它们共同定义使用同步筛选器的分配器类模板 `sync` 和类型为的缓存 `cache` 。

对于可以编译重新绑定的编译器，其生成的模板定义如下所示：

```cpp
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };
```

对于无法编译重新绑定的编译器，其生成的模板定义如下所示：

```cpp
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```

## <a name="cache_chunklist"></a><a name="cache_chunklist"></a> CACHE_CHUNKLIST

生成 `stdext::allocators::cache_chunklist<sizeof(Type)>`。

```cpp
#define CACHE_CHUNKLIST <cache_class>
```

### <a name="remarks"></a>备注

## <a name="cache_freelist"></a><a name="cache_freelist"></a> CACHE_FREELIST

生成 `stdext::allocators::cache_freelist<sizeof(Type), max>`。

```cpp
#define CACHE_FREELIST(max) <cache_class>
```

### <a name="remarks"></a>备注

## <a name="cache_suballoc"></a><a name="cache_suballoc"></a> CACHE_SUBALLOC

生成 `stdext::allocators::cache_suballoc<sizeof(Type)>`。

```cpp
#define CACHE_SUBALLOC <cache_class>
```

### <a name="remarks"></a>备注

## <a name="sync_default"></a><a name="sync_default"></a> SYNC_DEFAULT

生成同步筛选器。

```cpp
#define SYNC_DEFAULT <sync_template>
```

### <a name="remarks"></a>备注

如果编译器支持编译单线程和多线程应用程序，则对于单线程应用程序，宏生成 `stdext::allocators::sync_none`；在所有其他情况下生成 `stdext::allocators::sync_shared`。

## <a name="see-also"></a>请参阅

[\<allocators>](allocators-header.md)
