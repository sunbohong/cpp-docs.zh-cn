---
description: 了解详细信息：双重接口和事件
title: 双重接口和事件
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 231df7a0dfc8376acd6a9a0f9d85d0ed68fdd0b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153022"
---
# <a name="dual-interfaces-and-events"></a>双重接口和事件

虽然可以将事件接口设计为双重事件，但有很多合理的设计原因不会这样做。 基本原因是事件的源只通过 vtable 或 via `Invoke` （而不是两者）来激发事件。 如果事件源将事件作为直接 vtable 方法调用引发，则 `IDispatch` 永远不会使用这些方法，并且清楚地表明接口应该是纯粹的 vtable 接口。 如果事件源在调用时触发事件 `Invoke` ，则不会使用 vtable 方法，并清楚地表明接口应为调度接口。 如果将事件接口定义为 duals，则需要客户端实现不会使用的部分接口。

> [!NOTE]
> 通常，此参数不适用于双重接口。 从实现的角度来看，duals 是实现可由各种客户端访问的接口的一种快速、方便且支持的方式。

还有其他原因需要避免双重事件接口;Visual Basic 和 Internet Explorer 均不支持它们。

## <a name="see-also"></a>请参阅

[双重接口和 ATL](../atl/dual-interfaces-and-atl.md)
