---
title: OptICF 类
description: C++ Build Insights SDK OptICF 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptICF
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b816b53e1054c4492320bdb71f2f0c7726907cf4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920523"
---
# <a name="opticf-class"></a>OptICF 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`OptICF` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [OPT_ICF](../event-table.md#opt-icf) 事件。

## <a name="syntax"></a>语法

```cpp
class OptICF : public Activity
{
public:
    OptICF(const RawEvent& event);
};
```

## <a name="members"></a>成员

除了从自己的 [Activity](activity.md) 基类继承的成员外，`OptICF` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[OptICF](#opt-icf)

## <a name="opticf"></a><a name="opt-icf"></a> OptICF

```cpp
OptICF(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[OPT_ICF](../event-table.md#opt-icf) 事件。

::: moniker-end
