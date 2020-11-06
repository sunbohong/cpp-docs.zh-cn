---
title: EventGroup 类
description: C++ Build Insights SDK EventGroup 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 57cbc7a053132909149aee182b9560e2ee33c161
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923307"
---
# <a name="eventgroup-class"></a>EventGroup 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`EventGroup` 类模板是所有组捕获类的基类。

## <a name="syntax"></a>语法

```cpp
template <typename TActivity>
class EventGroup;
{
public:
    size_t Size() const;

    const TActivity& operator[](size_t index) const;
    const TActivity& Front() const;
    const TActivity& Back() const;

    std::deque<TActivity>::const_iterator begin() const;
    std::deque<TActivity>::const_iterator end() const;
};
```

### <a name="parameters"></a>参数

TActivity 组中包含的活动类型。

## <a name="members"></a>成员

### <a name="functions"></a>函数

[Back](#back)
[begin](#begin)
[end](#end)
[Front](#front)
[operator[]](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a> Back

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>返回值

对组中的最后一个活动事件的引用。

## <a name="begin"></a><a name="begin"></a> begin

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>返回值

指向活动事件组开头的迭代器。

## <a name="end"></a><a name="end"></a> end

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>返回值

指向超出活动事件组结尾的一个位置的迭代器。

## <a name="front"></a><a name="front"></a> Front

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>返回值

对组中的第一个活动事件的引用。

## <a name="operator"></a><a name="subscript-operator"></a> operator[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>参数

index\
要在活动事件组中访问的元素的索引。

### <a name="return-value"></a>返回值

存储在 index 指示的位置的事件堆栈的事件。

## <a name="size"></a><a name="size"></a> 大小

```cpp
size_t Size() const;
```

### <a name="return-value"></a>返回值

事件组的大小。

::: moniker-end
