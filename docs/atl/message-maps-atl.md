---
description: 了解详细信息： (ATL) 的消息映射
title: " (ATL) 的消息映射"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: c5b3340abbfbc66ac710ab716e3daa38dd7cd6df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159513"
---
# <a name="message-maps-atl"></a> (ATL) 的消息映射

消息映射将处理程序函数与特定消息、命令或通知关联起来。 通过使用 ATL 的 [消息映射宏](../atl/reference/message-map-macros-atl.md)，可以为窗口指定消息映射。 、和中的窗口过程 `CWindowImpl` `CDialogImpl` `CContainedWindowT` 将窗口的消息定向到其消息映射。

[消息处理程序函数](../atl/message-handler-functions.md)接受类型的其他参数 `BOOL&` 。 此参数指示消息是否已处理，并在默认情况下设置为 TRUE。 然后，处理函数可以将参数设置为 FALSE，以指示它未处理消息。 在这种情况下，ATL 将继续查找消息映射中的处理程序函数。 通过将此参数设置为 FALSE，你可以先执行某些操作来响应消息，然后允许默认处理或其他处理程序函数完成消息处理。

## <a name="chained-message-maps"></a>链式消息映射

ATL 还允许您链接消息映射，将消息处理定向到在另一个类中定义的消息映射。 例如，你可以在单独的类中实现常见消息处理，以便为所有与该类的 windows 链接提供统一的行为。 可以链接到基类或类的数据成员。

ATL 还支持动态链接，这允许您在运行时链接到另一个对象的消息映射。 若要实现动态链接，必须从 [CDynamicChain](../atl/reference/cdynamicchain-class.md)派生类。 然后在消息映射中声明 [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) 宏。 CHAIN_MSG_MAP_DYNAMIC 要求唯一的编号，用于标识要链接到的对象和消息映射。 必须通过调用来定义此唯一值 `CDynamicChain::SetChainEntry` 。

如果类派生自 [CMessageMap](../atl/reference/cmessagemap-class.md)，则可以链接到声明消息映射的任何类。 `CMessageMap` 允许对象向其他对象公开其消息映射。 请注意， `CWindowImpl` 已从派生 `CMessageMap` 。

## <a name="alternate-message-maps"></a>备用消息映射

最后，ATL 支持用 [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) 宏声明的替换消息映射。 每个备用消息映射都由一个唯一编号标识，该编号将传递给 ALT_MSG_MAP。 使用备用消息映射，可以在一个映射中处理多个窗口的消息。 请注意，默认情况下，不 `CWindowImpl` 使用替换消息映射。 若要添加此支持，请重写 `WindowProc` 派生类中的方法， `CWindowImpl` 并 `ProcessWindowMessage` 与消息映射标识符一起调用。

## <a name="see-also"></a>请参阅

[实现窗口](../atl/implementing-a-window.md)
