---
title: OptRef 类
description: C++ Build Insights SDK OptRef 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72d3867456ecc2bb643239ddb0186668e43f69ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920510"
---
# <a name="optref-class"></a>OptRef 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`OptRef` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [OPT_REF](../event-table.md#opt-ref) 事件。

## <a name="syntax"></a>语法

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>成员

除了从自己的 [Activity](activity.md) 基类继承的成员外，`OptRef` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[OptRef](#opt-ref)

## <a name="optref"></a><a name="opt-ref"></a> OptRef

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[OPT_REF](../event-table.md#opt-ref) 事件。

::: moniker-end
