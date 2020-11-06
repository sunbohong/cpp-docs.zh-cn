---
title: CommandLine 类
description: C++ Build Insights SDK CommandLine 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CommandLine
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5214f2970329510088184dc3092db66607f4d67e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923341"
---
# <a name="commandline-class"></a>CommandLine 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`CommandLine` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [COMMAND_LINE](../event-table.md#command-line) 事件。

## <a name="syntax"></a>语法

```cpp
class CommandLine : public SimpleEvent
{
public:
    CommandLine(const RawEvent& event);

    const wchar_t* Value() const;
};
```

## <a name="members"></a>成员

除了从自己的 [SimpleEvent](simple-event.md) 基类继承的成员外，`CommandLine` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[CommandLine](#command-line)

### <a name="functions"></a>函数

[值](#value)

## <a name="commandline"></a><a name="command-line"></a> CommandLine

```cpp
CommandLine(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[COMMAND_LINE](../event-table.md#command-line) 事件。

## <a name="value"></a><a name="value"></a> 值

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>返回值

包含命令行的字符串。 此值包括从响应文件中获取的参数，以及来自环境变量（如 CL、\_CL\_、Link 和 \_LINK\_）的参数。

::: moniker-end
