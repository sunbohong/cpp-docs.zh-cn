---
description: 了解详细信息：处理反射的消息
title: 处理反射消息
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 4093c2feaa263470bc07df6feec32b12fea01542
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254906"
---
# <a name="handling-reflected-messages"></a>处理反射消息

消息反射使你可以在控件本身中处理控件的消息，如 **WM_CTLCOLOR**、 **WM_COMMAND** 和 **WM_NOTIFY**。 这使得控件更独立和可移植。 此机制适用于 Windows 公共控件以及 ActiveX 控件（之前称为 OLE 控件）。

消息反射可以让您轻松地重用 `CWnd` 派生类。 消息反射通过 [CWnd：： OnChildNotify](reference/cwnd-class.md#onchildnotify)使用特殊 **ON_XXX_REFLECT** 消息映射项，例如 **ON_CTLCOLOR_REFLECT** 和 **ON_CONTROL_REFLECT**。 [技术说明 62](tn062-message-reflection-for-windows-controls.md) 更详细地说明了消息反射。

## <a name="what-do-you-want-to-do"></a>要执行的操作

- [了解有关消息反射的详细信息](tn062-message-reflection-for-windows-controls.md)

- [实现公共控件的消息反射](tn062-message-reflection-for-windows-controls.md)

- [实现 ActiveX 控件的消息反射](mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>请参阅

[声明消息处理程序函数](declaring-message-handler-functions.md)
