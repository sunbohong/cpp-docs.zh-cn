---
title: TemplateInstantiationGroup 类
description: C++ Build Insights SDK TemplateInstantiationGroup 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bacd48fbf15bfbbd768b527f42587425fb0932e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922970"
---
# <a name="templateinstantiationgroup-class"></a>TemplateInstantiationGroup 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`TemplateInstantiationGroup` 类与 [MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 事件组。

## <a name="syntax"></a>语法

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>成员

除了从自己的 [EventGroup\<TemplateInstantiation\>](event-group.md) 基类继承的成员外，`TemplateInstantiationGroup` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a> TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>参数

group\
一组 [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) 事件。

::: moniker-end
