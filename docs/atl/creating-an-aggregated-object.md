---
description: 了解详细信息：创建聚合对象
title: 创建聚合对象
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: e6efbf63e28d0477730a2d7c31ec91e9b75520e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153221"
---
# <a name="creating-an-aggregated-object"></a>创建聚合对象

聚合委托 `IUnknown` 调用，提供指向内部对象的外部对象的指针 `IUnknown` 。

## <a name="to-create-an-aggregated-object"></a>创建聚合对象

1. 添加 `IUnknown` 指向类对象的指针，并在构造函数中将其初始化为 NULL。

1. 重写 [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) 以创建聚合。

1. 使用 `IUnknown` 在步骤1中定义的指针作为 [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) 宏的第二个参数。

1. 重写 [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) 以释放 `IUnknown` 指针。

> [!NOTE]
> 如果在期间使用和释放聚合对象中的接口 `FinalConstruct` ，则应将 [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) 宏添加到类对象的定义。

## <a name="see-also"></a>请参阅

[ATL COM 对象的基本知识](../atl/fundamentals-of-atl-com-objects.md)
