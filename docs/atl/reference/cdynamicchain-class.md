---
description: 了解详细信息： CDynamicChain 类
title: CDynamicChain 类
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 5ada99b519900150afa2143fb1527245797fed98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141812"
---
# <a name="cdynamicchain-class"></a>CDynamicChain 类

此类提供支持消息映射的动态链接的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CDynamicChain
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDynamicChain::CDynamicChain](#cdynamicchain)|构造函数。|
|[CDynamicChain：： ~ CDynamicChain](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDynamicChain::CallChain](#callchain)|将 Windows 消息定向到另一对象的消息映射。|
|[CDynamicChain::RemoveChainEntry](#removechainentry)|从集合中移除消息映射项。|
|[CDynamicChain::SetChainEntry](#setchainentry)|向集合中添加消息映射项或修改现有项。|

## <a name="remarks"></a>备注

`CDynamicChain` 管理消息映射的集合，以便在运行时将 Windows 消息定向到另一对象的消息映射。

若要添加对动态消息映射链接的支持，请执行以下操作：

- 从派生类 `CDynamicChain` 。 在消息映射中，指定要链接到另一个对象的默认消息映射的 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 宏。

- 从 [CMessageMap](../../atl/reference/cmessagemap-class.md)派生要链接到的每个类。 `CMessageMap` 允许对象向其他对象公开其消息映射。

- 调用 `CDynamicChain::SetChainEntry` 以标识要链接到的对象和消息映射。

例如，假设你的类定义如下：

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

然后，客户端调用 `CMyWindow::SetChainEntry` ：

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

其中 `chainedObj` ，是链接对象，是派生自的类的实例 `CMessageMap` 。 现在，如果 `myCtl` 接收到不由或处理的消息 `OnPaint` `OnSetFocus` ，则窗口过程会将该消息定向到 `chainedObj` 的默认消息映射。

有关消息映射链接的详细信息，请参阅 "ATL 窗口类" 一文中的 [消息映射](../../atl/message-maps-atl.md) 。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="cdynamicchaincallchain"></a><a name="callchain"></a> CDynamicChain::CallChain

将 Windows 消息定向到另一对象的消息映射。

```
BOOL CallChain(
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```

### <a name="parameters"></a>parameters

*dwChainID*<br/>
中与链接的对象及其消息映射关联的唯一标识符。

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

### <a name="return-value"></a>返回值

如果消息已完全处理，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

若要调用窗口过程 `CallChain` ，必须在消息映射中指定 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 宏。 有关示例，请参阅 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 概述。

`CallChain` 需要对 [SetChainEntry](#setchainentry) 的前一次调用以将 *dwChainID* 值与对象及其消息映射相关联。

## <a name="cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a> CDynamicChain::CDynamicChain

构造函数。

```
CDynamicChain();
```

## <a name="cdynamicchaincdynamicchain"></a><a name="dtor"></a> CDynamicChain：： ~ CDynamicChain

析构函数。

```
~CDynamicChain();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

## <a name="cdynamicchainremovechainentry"></a><a name="removechainentry"></a> CDynamicChain::RemoveChainEntry

从集合中移除指定的消息映射。

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>parameters

*dwChainID*<br/>
中与链接的对象及其消息映射关联的唯一标识符。 最初通过调用 [SetChainEntry](#setchainentry)定义此值。

### <a name="return-value"></a>返回值

如果从集合中成功移除了消息映射，则为 TRUE。 否则为 FALSE。

## <a name="cdynamicchainsetchainentry"></a><a name="setchainentry"></a> CDynamicChain::SetChainEntry

向集合中添加指定的消息映射。

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>parameters

*dwChainID*<br/>
中与链接的对象及其消息映射关联的唯一标识符。

*pObject*<br/>
中指向声明消息映射的链接对象的指针。 此对象必须派生自 [CMessageMap](../../atl/reference/cmessagemap-class.md)。

*dwMsgMapID*<br/>
中链接的对象中的消息映射的标识符。 默认值为0，该值标识用 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)声明的默认消息映射。 若要指定使用 [ALT_MSG_MAP (msgMapID) ](message-map-macros-atl.md#alt_msg_map)声明的备用消息映射，请传递 `msgMapID` 。

### <a name="return-value"></a>返回值

如果消息映射已成功添加到集合，则为 TRUE。 否则为 FALSE。

### <a name="remarks"></a>备注

如果集合中已存在 *dwChainID* 值，则其关联的对象和消息映射将分别替换为 *pObject* 和 *dwMsgMapID*。 否则，将添加新条目。

## <a name="see-also"></a>请参阅

[CWindowImpl 类](../../atl/reference/cwindowimpl-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
