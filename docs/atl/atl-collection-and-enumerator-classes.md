---
description: 了解更多相关信息： ATL 集合和枚举器类
title: ATL 集合和枚举器类
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: b1f30aabb4908b0299a927f92a6d5ee4e9370a09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166039"
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL 集合和枚举器类

ATL 提供以下类来帮助您实现集合和枚举器。

|类|描述|
|-----------|-----------------|
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|集合接口实现|
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|枚举器接口实现 (假设存储在与 c + + 标准库兼容的容器中的数据) |
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|枚举器接口实现 (假设数组中存储的数据) |
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|枚举器对象实现 (使用 `IEnumOnSTLImpl`) |
|[CComEnum](../atl/reference/ccomenum-class.md)|枚举器对象实现 (使用 `CComEnumImpl`) |
|[_Copy](../atl/atl-copy-policy-classes.md)|复制策略类|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|复制策略类|
|[CAdapt](../atl/reference/cadapt-class.md)|适配器类 (隐藏 **操作员 &** 允许 `CComPtr` 、 `CComQIPtr` 和 `CComBSTR` 存储在 c + + 标准库容器中) |

## <a name="see-also"></a>请参阅

[集合和枚举数](../atl/atl-collections-and-enumerators.md)
