---
description: 了解详细信息：枚举器和集合类
title: " (ATL) 的枚举器和集合类"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- enumerators, ATL classes
ms.assetid: fcd093b2-98bf-444d-94ab-9a55520a5051
ms.openlocfilehash: a29c5c4a3923c7ba027845cecf0bb95d0a76ddb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152983"
---
# <a name="enumerators-and-collections-classes"></a>枚举器和集合类

以下类提供对 COM 集合和枚举的支持：

- [CComEnum](../atl/reference/ccomenum-class.md) 定义基于数组的 COM 枚举器对象。

- [CComEnumImpl](../atl/reference/ccomenumimpl-class.md) 提供 COM 枚举器接口的实现，其中所枚举的项存储在数组中。

- [CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md) 定义基于 c + + 标准库集合的 COM 枚举器对象。

- [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md) 提供要枚举的项存储在与 c + + 标准库兼容的容器中的 COM 枚举器接口的实现。

- [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md) 提供 `Count` `Item` 集合接口的、和属性的实现 `_NewEnum` 。

## <a name="related-articles"></a>相关文章

[ATL 集合和枚举器](../atl/atl-collections-and-enumerators.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)
