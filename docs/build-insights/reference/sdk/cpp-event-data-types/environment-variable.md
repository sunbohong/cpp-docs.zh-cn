---
title: EnvironmentVariable 类
description: C++ Build Insights SDK EnvironmentVariable 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f707ab744aaf6097975ba9e189815df3c9f32266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920758"
---
# <a name="environmentvariable-class"></a>EnvironmentVariable 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`EnvironmentVariable` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) 事件。

## <a name="syntax"></a>语法

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>成员

除了从自己的 [SimpleEvent](simple-event.md) 基类继承的成员外，`EnvironmentVariable` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>函数

[Name](#name)
[Value](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a> EnvironmentVariable

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable) 事件。

## <a name="name"></a><a name="name"></a> Name

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>返回值

环境变量的名称。

## <a name="value"></a><a name="value"></a> 值

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>返回值

环境变量的值。

::: moniker-end
