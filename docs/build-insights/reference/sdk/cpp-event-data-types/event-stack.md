---
title: EventStack 类
description: C++ Build Insights SDK EventStack 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4f1e92011acdf8272fe631843c03c2f960a1234
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920705"
---
# <a name="eventstack-class"></a>EventStack 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`EventStack` 类是 [Event](event.md) 对象的集合。 从 C++ Build Insights SDK 接收的所有事件都以 `EventStack` 对象的形式提供。 此堆栈中的最后一个条目是当前正在处理的事件。 最后一个条目之前的条目是当前事件的父层次结构。 有关 C++ Build Insights 中使用的事件模型的详细信息，请参阅[事件表](../event-table.md)。

## <a name="syntax"></a>语法

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

[EventStack](#event-stack)

### <a name="functions"></a>函数

[Back](#back)
[operator[]](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a> Back

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>返回值

一个 [RawEvent](raw-event.md) 对象，该对象表示堆栈中的最后一个条目。 事件堆栈中的最后一个条目是已触发的事件。

## <a name="eventstack"></a><a name="event-stack"></a> EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>参数

data\
从中生成 `EventStack` 的原始数据。

### <a name="remarks"></a>注解

通常不需要自行构造 `EventStack` 对象。 当在分析或重新记录会话过程中处理事件时，C++ Build Insights SDK 会向你提供这些对象。

## <a name="operator"></a><a name="subscript-operator"></a> operator[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>参数

index\
要在事件堆栈中访问的元素的索引。

### <a name="return-value"></a>返回值

一个 [RawEvent](raw-event.md) 对象，该对象表示存储在事件堆栈中 index 所指示位置的事件。

## <a name="size"></a><a name="size"></a> 大小

```cpp
size_t Size() const;
```

### <a name="return-value"></a>返回值

事件堆栈的大小。

::: moniker-end
