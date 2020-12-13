---
description: 了解有关以下内容的详细信息：实现双重接口
title: '实现双重接口 (ATL) '
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: e20bbe293cb7d6e7ae0f4d0482f1003571178ab9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147792"
---
# <a name="implementing-a-dual-interface"></a>实现双重接口

可以使用 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 类实现双重接口，该类提供 `IDispatch` 双重接口中的方法的默认实现。 有关详细信息，请参阅 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)。

使用此类：

- 在类型库中定义双重接口。

- 派生类 `IDispatchImpl` (将有关接口和类型库的信息传递) 的模板参数。

- 将一个条目 (或条目添加) 到 COM 映射，以便通过公开双重接口 `QueryInterface` 。

- 在类中实现接口的 vtable 部分。

- 确保包含接口定义的类型库在运行时可用于你的对象。

## <a name="atl-simple-object-wizard"></a>ATL 简单对象向导

如果要创建新的接口和新的类来实现它，则可以使用 " [Atl 添加类" 对话框](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box)，然后使用 [Atl 简单对象向导](../atl/reference/atl-simple-object-wizard.md)。

## <a name="implement-interface-wizard"></a>实现接口向导

如果你有现有的接口，则可以使用 " [实现接口向导](../atl/reference/adding-a-new-interface-in-an-atl-project.md) " 将必要的基类、COM 映射项和主干方法实现添加到现有类。

> [!NOTE]
> 您可能需要调整生成的基类，以便将类型库的主版本号和次版本号作为模板自变量传递给 `IDispatchImpl` 基类。 "实现接口" 向导不会为你检查类型库的版本号。

## <a name="implementing-idispatch"></a>实现 IDispatch

您可以使用 `IDispatchImpl` 基类来提供调度程序的实现，只需在 COM 映射中指定适当的条目 (使用 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 或 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) 宏) ，前提是您有一个描述对应双重接口的类型库。 `IDispatch`例如，以这种方式实现接口非常常见。 ATL 简单对象向导和实现接口向导都假设您打算以 `IDispatch` 这种方式实现，因此它们将向映射添加适当的条目。

> [!NOTE]
> ATL 提供了 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 和 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 类，可帮助实现调度接口，而无需包含与兼容双重接口的定义的类型库。

## <a name="see-also"></a>请参阅

[双重接口和 ATL](../atl/dual-interfaces-and-atl.md)
