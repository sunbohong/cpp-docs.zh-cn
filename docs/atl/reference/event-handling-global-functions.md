---
description: 了解详细信息：事件处理全局函数
title: 事件处理全局函数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
ms.openlocfilehash: 89e5ec38ff8884f5b99592541df6e397e2dd7116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139849"
---
# <a name="event-handling-global-functions"></a>事件处理全局函数

此函数提供事件处理程序。

> [!IMPORTANT]
> 下表中列出的函数不能用于在 Windows 运行时中执行的应用程序。

|名称|描述|
|-|-|
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|等待对象收到信号，同时根据需要调度窗口消息。|

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="atlwaitwithmessageloop"></a><a name="atlwaitwithmessageloop"></a> AtlWaitWithMessageLoop

等待发出对象信号，同时根据需要调度窗口消息。

> [!IMPORTANT]
> 此函数不能用于在 Windows 运行时中执行的应用程序。

```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```

### <a name="parameters"></a>parameters

*hEvent*<br/>
中要等待的对象的句柄。

### <a name="return-value"></a>返回值

如果对象已发出信号，则返回 TRUE。

### <a name="remarks"></a>备注

如果要等待对象的事件发生并通知其发生，但允许在等待时调度窗口消息，则此方法非常有用。

## <a name="see-also"></a>请参阅

[函数](../../atl/reference/atl-functions.md)
