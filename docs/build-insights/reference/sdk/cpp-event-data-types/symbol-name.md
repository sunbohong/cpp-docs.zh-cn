---
title: SymbolName 类
description: C++ Build Insights SDK SymbolName 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SymbolName
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a749d95b3812df8b1cc0cd7d2da037e98467cefc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920471"
---
# <a name="symbolname-class"></a>SymbolName 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`SymbolName` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [SYMBOL_NAME](../event-table.md#symbol-name) 事件。

## <a name="syntax"></a>语法

```cpp
class SymbolName : public SimpleEvent
{
public:
    SymbolName(const RawEvent& event);

    const unsigned long long&  Key() const;
    const char*                Name() const;
};
```

## <a name="members"></a>成员

除了从自己的 [SimpleEvent](simple-event.md) 基类继承的成员外，`SymbolName` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[SymbolName](#symbol-name)

### <a name="functions"></a>函数

[Key](#key)
[Name](#name)

## <a name="key"></a><a name="key"></a> Key

```cpp
const unsigned long long& Key() const;
```

### <a name="return-value"></a>返回值

由此符号表示的类型的数字标识符。 此标识符在编译器前端传递中是唯一的。

## <a name="name"></a><a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>返回值

由符号表示的类型的名称，用 UTF-8 编码。

## <a name="symbolname"></a><a name="symbol-name"></a> SymbolName

```cpp
SymbolName(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[SYMBOL_NAME](../event-table.md#symbol-name) 事件。

::: moniker-end
