---
description: 了解详细信息：向复合控件添加功能
title: 向复合控件添加功能
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 90e1f6b0adfc33817f9fa5a6de6fbdcd276241e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166117"
---
# <a name="adding-functionality-to-the-composite-control"></a>向复合控件添加功能

将任何所需的控件插入复合控件后，下一步就是添加新功能。 此新功能通常分为两类：

- 支持其他接口，并通过其他特定功能自定义复合控件的行为。

- 处理包含的 ActiveX 控件中的事件 (或控件) 。

在本文的目的和范围内，本部分的其余部分只是处理来自 ActiveX 控件的事件。

> [!NOTE]
> 如果需要处理来自 Windows 控件的消息，请参阅 [实现窗口](../atl/implementing-a-window.md) ，了解有关 ATL 中消息处理的详细信息。

在对话框资源中插入 ActiveX 控件后，右键单击控件，然后单击 " **添加事件处理程序**"。 选择要处理的事件，然后单击 " **添加" 和 "编辑**"。 事件处理程序代码将添加到控件的 .h 文件中。

复合控件上 ActiveX 控件的连接点通过对 [CComCompositeControl：： AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)的调用自动连接和断开连接。

## <a name="see-also"></a>请参阅

[复合控件基础知识](../atl/atl-composite-control-fundamentals.md)
