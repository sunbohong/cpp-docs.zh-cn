---
title: ForceInlinee 类
description: C++ Build Insights SDK ForceInlinee 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 53fff7b6cfd37ba3e3211dd072c1ce3386d00fda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920666"
---
# <a name="forceinlinee-class"></a>ForceInlinee 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`ForceInlinee` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [FORCE_INLINEE](../event-table.md#force-inlinee) 事件。

## <a name="syntax"></a>语法

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>成员

除了从自己的 [SimpleEvent](simple-event.md) 基类继承的成员外，`ForceInlinee` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[ForceInlinee](#force-inlinee)

### <a name="functions"></a>函数

[Name](#name)
[Size](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a> ForceInlinee

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[FORCE_INLINEE](../event-table.md#force-inlinee) 事件。

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>返回值

强制内联函数的名称，以 UTF-8 编码。

## <a name="size"></a><a name="size"></a> 大小

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>返回值

强制内联函数的大小，作为中间指令计数。

::: moniker-end
