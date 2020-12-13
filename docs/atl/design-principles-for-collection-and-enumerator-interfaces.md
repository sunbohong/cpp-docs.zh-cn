---
description: 了解详细信息：集合和枚举器接口的设计原则
title: " (ATL) 设计集合和枚举器接口"
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
ms.openlocfilehash: effd2cce775ef926befc89bb6b72a976d85bdf23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148000"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>集合和枚举器接口的设计原则

每种类型的接口都有不同的设计原则：

- 集合接口提供了通过方法 *随机* 访问集合中的 *单个* 项的权限 `Item` ，它允许客户端通过属性发现集合中的项数 `Count` ，并经常允许客户端添加和删除项。

- 枚举器接口提供对集合中 *多个* 项的 *串行* 访问，它不允许客户端在枚举器停止返回项) 之前，发现集合中有多少项 (，并且它不提供添加或删除项的任何方式。

每种类型的接口在提供对集合中元素的访问时起到不同的作用。

## <a name="see-also"></a>请参阅

[集合和枚举数](../atl/atl-collections-and-enumerators.md)
