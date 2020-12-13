---
description: 了解详细信息： CMessageMap 类
title: CMessageMap 类
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: 90ecdc101071b84362d328558ff2e74cb9bbeb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141435"
---
# <a name="cmessagemap-class"></a>CMessageMap 类

此类允许其他对象访问对象的消息映射。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMessageMap：:P rocessWindowMessage](#processwindowmessage)|访问派生类中的消息映射 `CMessageMap` 。|

## <a name="remarks"></a>备注

`CMessageMap` 是一个抽象基类，它允许其他对象访问对象的消息映射。 为了使对象公开其消息映射，其类必须派生自 `CMessageMap` 。

ATL 使用 `CMessageMap` 来支持包含的窗口和动态消息映射链接。 例如，包含 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 对象的任何类必须派生自 `CMessageMap` 。 下面的代码来自 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) 示例。 通过 [CComControl](../../atl/reference/ccomcontrol-class.md)， `CAtlEdit` 类会自动派生自 `CMessageMap` 。

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

由于包含的窗口 `m_EditCtrl` 将使用包含类中的消息映射， `CAtlEdit` 派生自 `CMessageMap` 。

有关消息映射的详细信息，请参阅 "ATL 窗口类" 一文中的 [消息映射](../../atl/message-maps-atl.md) 。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a> CMessageMap：:P rocessWindowMessage

访问派生类中由 *dwMsgMapID* 标识的消息映射 `CMessageMap` 。

```
virtual BOOL ProcessWindowMessage(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```

### <a name="parameters"></a>parameters

*hWnd*<br/>
中接收消息的窗口的句柄。

*uMsg*<br/>
中发送到窗口的消息。

*wParam*<br/>
中其他特定于消息的信息。

*lParam*<br/>
中其他特定于消息的信息。

*lResult*<br/>
弄消息处理的结果。

*dwMsgMapID*<br/>
中将处理消息的消息映射的标识符。 使用 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)声明的默认消息映射由0标识。 使用 [ALT_MSG_MAP (msgMapID) ](message-map-macros-atl.md#alt_msg_map)声明的备用消息映射由标识 `msgMapID` 。

### <a name="return-value"></a>返回值

如果消息完全处理，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

由 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 对象的窗口过程或动态链接到消息映射的对象调用。

## <a name="see-also"></a>请参阅

[CDynamicChain 类](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP (msgMapID) ](message-map-macros-atl.md#alt_msg_map)<br/>
[类概述](../../atl/atl-class-overview.md)
