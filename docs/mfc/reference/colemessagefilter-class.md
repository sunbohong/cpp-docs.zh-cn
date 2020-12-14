---
description: 了解详细信息： COleMessageFilter 类
title: COleMessageFilter 类
ms.date: 11/04/2016
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
ms.openlocfilehash: f0ab1d473704f5355933c04072a195c12fb71c73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226891"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter 类

管理 OLE 应用程序交互所需的并发。

## <a name="syntax"></a>语法

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|构造 `COleMessageFilter` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[COleMessageFilter::BeginBusyState](#beginbusystate)|使应用程序处于繁忙状态。|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|启用和禁用当被调用的应用程序繁忙时显示的对话框。|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|启用和禁用当被调用应用程序未响应时显示的对话框。|
|[COleMessageFilter::EndBusyState](#endbusystate)|终止应用程序的忙状态。|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|在 OLE 调用进行过程中，由框架调用以处理消息。|
|[COleMessageFilter：： Register](#register)|向 OLE 系统 Dll 注册消息筛选器。|
|[COleMessageFilter：： Revoke](#revoke)|撤消对 OLE 系统 Dll 的消息筛选器注册。|
|[COleMessageFilter::SetBusyReply](#setbusyreply)|确定忙应用程序对 OLE 调用的答复。|
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|确定应用程序等待 OLE 调用响应的时间。|
|[COleMessageFilter::SetRetryReply](#setretryreply)|确定调用应用程序对繁忙应用程序的答复。|

## <a name="remarks"></a>备注

`COleMessageFilter`类在视觉对象编辑服务器和容器应用程序以及 OLE 自动化应用程序中非常有用。 对于被调用的服务器应用程序，此类可用于使应用程序处于 "忙碌" 状态，以便以后可以取消或重试来自其他容器应用程序的传入调用。 此类还可用于确定调用应用程序在被调用的应用程序繁忙时要执行的操作。

通常，服务器应用程序调用 [BeginBusyState](#beginbusystate) 和 [EndBusyState](#endbusystate) 时，如果文档或其他 OLE 辅助功能对象被破坏，则会很危险。 用户界面更新期间，在 [CWinApp：： OnIdle](../../mfc/reference/cwinapp-class.md#onidle) 中进行这些调用。

默认情况下， `COleMessageFilter` 初始化应用程序时将分配对象。 可以通过 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)检索它。

这是一个高级类;您很少需要直接使用。

有关详细信息，请参阅文章 [服务器：实现服务器](../../mfc/servers-implementing-a-server.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>要求

**标头：** afxole

## <a name="colemessagefilterbeginbusystate"></a><a name="beginbusystate"></a> COleMessageFilter::BeginBusyState

调用此函数以开始忙状态。

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>备注

它与 [EndBusyState](#endbusystate) 结合使用，以控制应用程序的忙状态。 函数 [SetBusyReply](#setbusyreply) 确定应用程序在忙时调用应用程序的答复。

`BeginBusyState`和 `EndBusyState` 分别调用递增和递减，以确定应用程序是否繁忙。 例如，对和的两次调用 `BeginBusyState` 仍将 `EndBusyState` 导致繁忙状态。 若要取消繁忙状态，需要调用 `EndBusyState` 相同的次数调用 `BeginBusyState` 。

默认情况下，该框架在空闲处理期间进入忙状态，该状态由 [CWinApp：： OnIdle](../../mfc/reference/cwinapp-class.md#onidle)执行。 当应用程序处理 ON_COMMANDUPDATEUI 通知时，将在空闲处理完成后处理传入调用。

## <a name="colemessagefiltercolemessagefilter"></a><a name="colemessagefilter"></a> COleMessageFilter::COleMessageFilter

创建一个 `COleMessageFilter` 对象。

```
COleMessageFilter();
```

## <a name="colemessagefilterenablebusydialog"></a><a name="enablebusydialog"></a> COleMessageFilter::EnableBusyDialog

启用和禁用 "忙碌" 对话框，该对话框在消息挂起延迟过期时显示 (在 OLE 调用期间请参阅 [SetRetryReply](#setretryreply)) 。

```cpp
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>parameters

*bEnableBusy*<br/>
指定是否启用或禁用 "忙" 对话框。

## <a name="colemessagefilterenablenotrespondingdialog"></a><a name="enablenotrespondingdialog"></a> COleMessageFilter::EnableNotRespondingDialog

启用和禁用 "未响应" 对话框，在 OLE 调用期间，如果某个键盘或鼠标消息处于挂起状态，并且调用超时，则会显示此对话框。

```cpp
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>parameters

*bEnableNotResponding*<br/>
指定是否启用或禁用 "未响应" 对话框。

## <a name="colemessagefilterendbusystate"></a><a name="endbusystate"></a> COleMessageFilter::EndBusyState

调用此函数以结束繁忙状态。

```
virtual void EndBusyState();
```

### <a name="remarks"></a>备注

它与 [BeginBusyState](#beginbusystate) 结合使用，以控制应用程序的忙状态。 函数 [SetBusyReply](#setbusyreply) 确定应用程序在忙时调用应用程序的答复。

`BeginBusyState`和 `EndBusyState` 分别调用递增和递减，以确定应用程序是否繁忙。 例如，对和的两次调用 `BeginBusyState` 仍将 `EndBusyState` 导致繁忙状态。 若要取消繁忙状态，需要调用 `EndBusyState` 相同的次数调用 `BeginBusyState` 。

默认情况下，该框架在空闲处理期间进入忙状态，该状态由 [CWinApp：： OnIdle](../../mfc/reference/cwinapp-class.md#onidle)执行。 当应用程序处理 ON_UPDATE_COMMAND_UI 通知时，将在空闲处理完成后处理传入调用。

## <a name="colemessagefilteronmessagepending"></a><a name="onmessagepending"></a> COleMessageFilter::OnMessagePending

在 OLE 调用进行过程中，由框架调用以处理消息。

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>parameters

*pMsg*<br/>
指向挂起消息的指针。

### <a name="return-value"></a>返回值

若成功，则为非零；否则为 0。

### <a name="remarks"></a>备注

当调用应用程序等待调用完成时，框架将调用 `OnMessagePending` 并带有指向挂起消息的指针。 默认情况下，框架调度 WM_PAINT 消息，以便在花费较长时间的调用期间可以发生窗口更新。

必须通过调用 [注册](#register) 来注册消息筛选器，然后才能使其成为活动状态。

## <a name="colemessagefilterregister"></a><a name="register"></a> COleMessageFilter：： Register

向 OLE 系统 Dll 注册消息筛选器。

```
BOOL Register();
```

### <a name="return-value"></a>返回值

若成功，则为非零；否则为 0。

### <a name="remarks"></a>备注

消息筛选器不起作用，除非向系统 Dll 注册它。 通常，应用程序的初始化代码会注册应用程序的消息筛选器。 您的应用程序注册的任何其他消息筛选器都应在程序通过调用 [Revoke](#revoke)终止之前被撤消。

框架的默认消息筛选器会在初始化期间自动注册，并在终止时撤销。

## <a name="colemessagefilterrevoke"></a><a name="revoke"></a> COleMessageFilter：： Revoke

撤消通过调用 [Register](#register)执行的上一个注册。

```cpp
void Revoke();
```

### <a name="remarks"></a>备注

在程序终止之前，应撤消消息筛选器。

框架自动创建并注册的默认消息筛选器也会自动吊销。

## <a name="colemessagefiltersetbusyreply"></a><a name="setbusyreply"></a> COleMessageFilter::SetBusyReply

此函数设置应用程序的 "繁忙答复"。

```cpp
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>parameters

*nBusyReply*<br/>
一个来自枚举的值 `SERVERCALL` ，该值是在 COMPOBJ 中定义的。 它可以具有下列值之一：

- SERVERCALL_ISHANDLED 应用程序可以接受调用，但处理特定调用可能会失败。

- SERVERCALL_REJECTED 应用程序可能永远无法处理调用。

- SERVERCALL_RETRYLATER 应用程序暂时处于无法处理调用的状态。

### <a name="remarks"></a>备注

[BeginBusyState](#beginbusystate)和[EndBusyState](#endbusystate)函数控制应用程序的忙状态。

当应用程序忙于调用时 `BeginBusyState` ，它会响应从 OLE 系统 dll 发出的调用，其值由的最后一个设置确定 `SetBusyReply` 。 调用应用程序使用此忙回复来确定要执行的操作。

默认情况下，将 SERVERCALL_RETRYLATER 繁忙的答复。 此答复会导致调用应用程序尽快重试呼叫。

## <a name="colemessagefiltersetmessagependingdelay"></a><a name="setmessagependingdelay"></a> COleMessageFilter::SetMessagePendingDelay

确定在采取进一步操作之前，调用应用程序等待来自被调用应用程序的响应的时间长度。

```cpp
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>parameters

*nTimeout*<br/>
消息挂起延迟的毫秒数。

### <a name="remarks"></a>备注

此函数与 [SetRetryReply](#setretryreply)配合使用。

## <a name="colemessagefiltersetretryreply"></a><a name="setretryreply"></a> COleMessageFilter::SetRetryReply

确定调用应用程序从被调用应用程序收到繁忙响应时的操作。

```cpp
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>parameters

*nRetryReply*<br/>
两次重试之间的毫秒数。

### <a name="remarks"></a>备注

当被调用的应用程序指示它处于繁忙状态时，调用应用程序可能会决定等待服务器不再忙、立即重试，或在指定的间隔后重试。 它还可能决定取消调用。

调用方的响应由函数 `SetRetryReply` 和 [SetMessagePendingDelay](#setmessagependingdelay)控制。 `SetRetryReply` 确定调用应用程序在给定调用的重试之间应等待多长时间。 `SetMessagePendingDelay` 确定在采取进一步操作之前，调用应用程序等待来自服务器的响应的时间。

通常，默认值是可接受的，无需更改。 此框架每隔 *nRetryReply* 毫秒重试一次调用，直到调用结束或消息挂起延迟过期。 如果 *nRetryReply* 的值为0，则指定立即重试，-1 指定取消调用。

当消息挂起延迟过期时，将显示 "忙" 对话框 (参阅 [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) ，以使用户可以选择取消或重试呼叫。 调用 [EnableBusyDialog](#enablebusydialog) 可启用或禁用此对话框。

当某个键盘或鼠标消息在调用期间处于挂起状态，并且调用超时 (超过消息挂起延迟) 时，将显示 "未响应" 对话框。 调用 [EnableNotRespondingDialog](#enablenotrespondingdialog) 可启用或禁用此对话框。 通常，这种事务状态表明出现了问题，用户正在获取缺乏耐心。

当对话框处于禁用状态时，当前 "重试答复" 始终用于调用繁忙的应用程序。

## <a name="see-also"></a>请参阅

[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)
