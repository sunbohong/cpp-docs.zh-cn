---
description: 了解详细信息： COM 简介
title: COM 简介
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
ms.openlocfilehash: 635bce8c1214dddfc258ae6d2d6c7e751f778e9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147662"
---
# <a name="introduction-to-com"></a>COM 简介

COM 是在其上构建 ActiveX 控件和 OLE 的基本 "对象模型"。 COM 允许对象向其他组件和主机应用程序公开其功能。 它定义对象自身的公开方式以及此公开跨各个进程和跨网络的方式。 COM 还定义了对象的生命周期。

COM 的基础是以下概念：

- [接口](../atl/interfaces-atl.md) —对象公开其功能的机制。

- [IUnknown](../atl/iunknown.md) —所有其他人所基于的基本接口。 它实现通过 COM 运行的引用计数和接口查询机制。

- [引用计数](../atl/reference-counting.md) -一种方法，该方法严格地 (或、接口) 决定何时不再使用，因此可以随意删除。

- [QueryInterface](../atl/queryinterface.md) —用于查询给定接口的对象的方法。

- [封送处理](../atl/marshaling.md) -一种机制，该机制允许跨线程、进程和网络边界使用对象，从而实现位置独立性。

- [聚合](../atl/aggregation.md) -一个对象可以利用另一个对象的方法。

## <a name="see-also"></a>请参阅

[COM 和 ATL 简介](../atl/introduction-to-com-and-atl.md)<br/>
[组件对象模型](/windows/win32/com/the-component-object-model)
