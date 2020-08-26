---
title: 任何类
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: defec0f6ab8f59219afddcefc67ea93435347978
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844738"
---
# <a name="any-class"></a>任何类

存储满足构造函数要求或没有值的任何类型的实例，该实例称为类的任何对象的状态。

存储的实例称为包含的值。 如果两个状态都没有值，或者两者都具有值并且包含的值相同，则这两个状态是相同的。

## <a name="syntax"></a>语法

```cpp
class any
```

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|名称|说明|
|-|-|
|[随时](#any)|构造 `any` 类型的对象。|

### <a name="functions"></a>函数

|名称|说明|
|-|-|
|[emplace](#emplace)|设置任意值。|
|[has_value](#has_value)|**`true`** 如果有值，则返回。|
|[reset](#reset)|重置 any。|
|[swap](#swap)|交换两个对象。|
|[type](#type)|返回任何类型。|

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator =](#op_eq)|将 any 替换为另一个的副本。|

## <a name="any"></a><a name="any"></a> 随时

构造 `any` 类型的对象。 还包含析构函数。

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a><a name="emplace"></a> emplace

设置任意值。

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a><a name="has_value"></a> has_value

**`true`** 如果有值，则返回。

```cpp
bool has_value() const noexcept;
```

## <a name="operator"></a><a name="op_eq"></a> operator =

将 any 替换为另一个的副本。

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>参数

*然后*\
正在复制到 any 的。

## <a name="reset"></a><a name="reset"></a> &

重置 any。

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a> 购

交换两个对象。

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a><a name="type"></a> 类型

返回任何类型。

```cpp
const type_info& type() const noexcept;
```
