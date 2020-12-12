---
description: 了解详细信息：聚合
title: 聚合
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
ms.openlocfilehash: fb02dd399020f8768fcdb3cc86687578e51cb3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166091"
---
# <a name="aggregation"></a>聚合

有时，对象的实现器要利用另一个预先生成的对象提供的服务。 此外，它还会将第二个对象作为第一个对象的一个自然部分显示。 COM 通过包含和聚合来实现这两个目标。

聚合意味着包含 (外部) 对象的包含 (内部) 对象作为其创建进程的一部分创建，内部对象的接口由外部公开。 对象允许自身可聚合。 如果是，则必须遵循特定的聚合规则才能正常工作。

主要是， `IUnknown` 包含对象上的所有方法调用都必须委托给包含对象。

## <a name="see-also"></a>请参阅

[COM 简介](../atl/introduction-to-com.md)<br/>
[重用对象](/windows/win32/com/reusing-objects)
