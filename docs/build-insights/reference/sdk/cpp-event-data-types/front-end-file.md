---
title: FrontEndFile 类
description: C++ Build Insights SDK FrontEndFile 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7715a153df538eab94b8de5281a91d4f6b439ff9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920653"
---
# <a name="frontendfile-class"></a>FrontEndFile 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFile` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配 [FRONT_END_FILE](../event-table.md#front-end-file) 事件。

## <a name="syntax"></a>语法

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>成员

除了从自己的 [Activity](activity.md) 基类继承的成员外，`FrontEndFile` 类还包含以下成员：

### <a name="constructors"></a>构造函数

[FrontEndFile](#front-end-file)

### <a name="functions"></a>函数

[路径](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a> FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
[FRONT_END_FILE](../event-table.md#front-end-file) 事件。

## <a name="path"></a><a name="path"></a> Path

```cpp
const char* Path() const;
```

### <a name="return-value"></a>返回值

文件的绝对路径，以 UTF-8 编码。

::: moniker-end
