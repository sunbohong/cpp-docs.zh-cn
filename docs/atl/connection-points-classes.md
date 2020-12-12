---
description: 了解详细信息：连接点类
title: '连接点类 (ATL) '
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 28d41f15aeafd98c8c9bcac27fde25d0b2037765
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148234"
---
# <a name="connection-points-classes"></a>连接点类

以下类提供对连接点的支持：

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) 实现连接点容器。

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 实现连接点。

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 实现表示 [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 接口的连接点。

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) 管理连接点与其接收器之间的无限连接。

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) 管理连接点与其接收器之间的固定数目的连接。

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) 通知客户端的接收器，对象的属性已更改或即将发生更改。

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 为 ATL COM 对象的连接点提供支持。 这些连接点通过事件接收器映射进行映射，该映射由您的 COM 对象提供。

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 与类中的事件接收器映射结合使用，以将事件路由到适当的处理程序函数。

## <a name="related-articles"></a>相关文章

[连接点](../atl/atl-connection-points.md)

[事件处理和 ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)<br/>
[连接点宏](../atl/reference/connection-point-macros.md)<br/>
[连接点全局函数](../atl/reference/connection-point-global-functions.md)
