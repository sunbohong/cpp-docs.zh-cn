---
title: RELOG_CALLBACKS 结构
description: C++ Build Insights SDK RELOG_CALLBACKS 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b3beb656aa72ce4c8519c56c4c8bf6ca6577cf4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919794"
---
# <a name="relog_callbacks-structure"></a>RELOG_CALLBACKS 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

初始化 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 对象时使用 `RELOG_CALLBACKS` 结构。 它指定在重新记录 Windows 事件跟踪 (ETW) 跟踪期间要调用的函数。

## <a name="syntax"></a>语法

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `OnStartActivity` | 调用以处理活动启动事件。 |
| `OnStopActivity` | 调用以处理活动停止事件。 |
| `OnSimpleEvent` | 调用以处理简单事件。 |
| `OnTraceInfo` | 在重新记录传递开始时，在调用 `OnBeginReloggingPass` 之后调用一次。 |
| `OnBeginRelogging` | 在开始重新记录会话时，在重新记录传递开始之前调用。 |
| `OnEndRelogging` | 在终止重新记录会话时，在重新记录传递结束后调用。 |
| `OnBeginReloggingPass` | 在开始重新记录传递时，在处理任何事件之前调用。 |
| `OnEndReloggingPass` | 在终止重新记录传递时，在处理完所有事件后调用。 |

## <a name="remarks"></a>备注

`RELOG_CALLBACKS` 结构的所有成员都必须指向有效函数。 有关接受的函数签名的详细信息，请参阅 [OnRelogEventFunc](on-relog-event-func-typedef.md)、[OnTraceInfoFunc](on-trace-info-func-typedef.md) 和 [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)。

::: moniker-end
