---
title: default_delete 结构
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 8baa9f5d294cf083fd55414cd529e438f328d1a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845076"
---
# <a name="default_delete-struct"></a>default_delete 结构

一个预定义的函数对象，它对其参数 () 执行除法运算 `operator/` 。

## <a name="syntax"></a>语法

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>要求

**标头：**\<memory>

**命名空间:** std

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|名称|说明|
|-|-|
|[default_delete](#default_delete)|`default_delete` 类型的对象的构造函数。|

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[运算符 ( # B1 ](#op_paren)|要访问的引用运算符 `default_delete` 。|

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

`default_delete` 类型的对象的构造函数。

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="operator"></a><a name="op_paren"></a> 运算符 ( # A1

要访问的引用运算符 `default_delete` 。

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>另请参阅

[\<memory>](../standard-library/memory.md)
