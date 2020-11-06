---
title: ExecutableImageOutput 类
description: C++ Build Insights SDK ExecutableImageOutput 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bf6bb9790dabc39d1ed6baa417d5dc3bf72ed5e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920718"
---
# <a name="executableimageoutput-class"></a>ExecutableImageOutput 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`ExecutableImageOutput` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) 事件。

## <a name="syntax"></a>语法

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>成员

除了从自己的 [FileOutput](file-output.md) 基类继承的成员外，`ExecutableImageOutput` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[ExecutableImageOutput](#executable-image-output)

## <a name="executableimageoutput"></a><a name="executable-image-output"></a> ExecutableImageOutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) 事件。

::: moniker-end
