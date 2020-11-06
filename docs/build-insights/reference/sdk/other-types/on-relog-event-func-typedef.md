---
title: OnRelogEventFunc typedef
description: C++ Build Insights SDK OnRelogEventFunc typedef 引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ed639ab59b900f97d29dc69240e45b2f52f2f3b3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919743"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`OnRelogEventFunc` typedef 是在 [RELOG_CALLBACKS](relog-callbacks-struct.md) 结构中使用的函数签名之一。

## <a name="syntax"></a>语法

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>参数

eventStack\
当前事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

relogSession\
调用 [InjectEvent](../functions/inject-event.md) 时使用的重新记录会话指针。

callbackContext\
在 [RELOG_DESCRIPTOR](analysis-descriptor-struct.md) 中为此回调设置的上下文值。

### <a name="return-value"></a>返回值

控制接下来应执行的操作的 [CALLBACK_CODE](callback-code-enum.md) 值。

::: moniker-end
