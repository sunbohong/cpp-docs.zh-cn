---
title: pointer_traits 结构
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
ms.openlocfilehash: 1ed8d61a52c11ab48fe6f762ff342ea88d107b14
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832693"
---
# <a name="pointer_traits-struct"></a>pointer_traits 结构

提供类型的对象所需的信息， `allocator_traits` 以描述带有指针类型的分配器 `Ptr` 。

## <a name="syntax"></a>语法

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>备注

Ptr 可以是 `Ty *` 类型的原始指针或具有以下属性的类。

```cpp
struct Ptr
{ // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj); // optional
};
```

## <a name="members"></a>成员

### <a name="typedefs"></a>Typedef

|名称|说明|
|-|-|
|`typedef T2 difference_type`|如果 `Ptr::difference_type` 类型存在，则类型 `T2` 为此类型，否则为 `ptrdiff_t`。 如果 `Ptr` 是原始指针，则类型为 `ptrdiff_t`。|
|`typedef T1 element_type`|如果 `Ptr::element_type` 类型存在，则类型 `T1` 为此类型，否则为 `Ty`。 如果 `Ptr` 是原始指针，则类型为 `Ty`。|
|`typedef Ptr pointer`|类型为 `Ptr`。|

### <a name="structs"></a>结构

|名称|说明|
|-|-|
|`rebind`|尝试将基础指针类型转换为指定类型。|

### <a name="methods"></a>方法

|名称|说明|
|----------|-----------------|
|[pointer_to](#pointer_to)|将任意引用转换为 `Ptr` 类的对象。|

### <a name="pointer_to"></a><a name="pointer_to"></a> pointer_to

存在 `Ptr::pointer_to(obj)` 时，则为返回该函数的静态方法。 否则，无法将任意引用转换为 `Ptr` 类的对象。 如果 `Ptr` 是原始指针，则此方法将返回 `addressof(obj)`。

```cpp
static pointer pointer_to(element_type& obj);
```
