---
title: Linker 类
description: C++ Build Insights SDK Linker 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf5544d725c12db8962d888944d4a281387207fa
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923092"
---
# <a name="linker-class"></a>Linker 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`Linker` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [LINKER](../event-table.md#linker) 事件。

## <a name="syntax"></a>语法

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>成员

除了从自己的 [Invocation](invocation.md) 基类继承的成员外，`Linker` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[链接器](#linker)

## <a name="linker"></a><a name="linker"></a> Linker

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[LINKER](../event-table.md#linker) 事件。

::: moniker-end
