---
title: InvocationGroup 类
description: C++ Build Insights SDK InvocationGroup 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a8d4786a228ab25551ee36ce22637d44dc07307
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920627"
---
# <a name="invocationgroup-class"></a>InvocationGroup 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`InvocationGroup` 类与 [MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配包含 [COMPILER](../event-table.md#compiler) 和 [LINKER](../event-table.md#linker) 事件的组合的组。

## <a name="syntax"></a>语法

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>成员

除了从自己的 [EventGroup\<Invocation\>](event-group.md) 基类继承的成员外，`InvocationGroup` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[InvocationGroup](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a> InvocationGroup

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>参数

group\
包含 [COMPILER](../event-table.md#compiler) 和 [LINKER](../event-table.md#linker) 事件的组合的组。

::: moniker-end
