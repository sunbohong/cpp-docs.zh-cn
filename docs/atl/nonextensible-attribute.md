---
title: nonextensible 特性
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: fda2a0d43144b6e9832e061e7198b3f3e65f8b86
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500111"
---
# <a name="nonextensible-attribute"></a>nonextensible 特性

如果在运行时不会扩展双重接口 (即，你不会通过 vtable) 提供方法或属性 `IDispatch::Invoke` ，你应将 **nonextensible** 属性应用于接口定义。 此属性为客户端语言提供信息 (例如 Visual Basic) ，这些信息可用于在编译时启用完整代码验证。 如果未提供此属性，则在运行时之前，bug 可能会在客户端代码中保持隐藏状态。

有关 **nonextensible** 属性和示例的详细信息，请参阅 [nonextensible](../windows/attributes/nonextensible.md)。

## <a name="see-also"></a>请参阅

[双重接口和 ATL](../atl/dual-interfaces-and-atl.md)
