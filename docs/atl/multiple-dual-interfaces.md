---
description: 了解详细信息：多个双重接口
title: 多个双重接口
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
ms.openlocfilehash: d90c0176b3165cc0e5b976a29ec58b58fd3a7a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159410"
---
# <a name="multiple-dual-interfaces"></a>多个双重接口

你可能想要将双重接口 (的优点结合起来，这就是 vtable 和后期绑定的灵活性，从而使类可用于脚本语言和 c + +) ，并提供多重继承技术。

尽管可以在一个 COM 对象上公开多个双重接口，但不建议这样做。 如果有多个双重接口，则必须只公开一个 `IDispatch` 接口。 用于确保这种情况的方法是使用损失，如函数丢失或代码复杂性增加。 考虑这种方法的开发人员应认真权衡优点和缺点。

## <a name="exposing-a-single-idispatch-interface"></a>公开单个 IDispatch 接口

通过从两个或更多的专用化派生，可以在单个对象上公开多个双重接口 `IDispatchImpl` 。 但是，如果你允许客户端查询 `IDispatch` 接口，则需要使用 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 宏 (或 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid)) # A2 来指定要用于实现的基类 `IDispatch` 。

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

由于只 `IDispatch` 公开了一个接口，只能通过接口访问你的对象的客户端 `IDispatch` 将不能访问任何其他接口中的方法或属性。

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>将多个双重接口合并为 IDispatch 的单一实现

ATL 不提供将多个双重接口组合成单个实现的任何支持 `IDispatch` 。 但是，有几种方法可用于手动组合接口，例如创建一个模板类，其中包含单独接口的联合 `IDispatch` 、创建新对象来执行 `QueryInterface` 函数，或使用嵌套对象的基于 typeinfo 的实现来创建 `IDispatch` 接口。

这些方法可能会导致命名空间冲突以及代码复杂性和可维护性。 不建议创建多个双重接口。

## <a name="see-also"></a>请参阅

[双重接口和 ATL](../atl/dual-interfaces-and-atl.md)
