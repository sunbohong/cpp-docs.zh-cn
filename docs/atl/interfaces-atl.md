---
description: 了解详细信息： (ATL) 的接口
title: 接口 (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: d68f482d05ff828631f5f9f27085f24af188d643
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147688"
---
# <a name="interfaces-atl"></a>接口 (ATL)

接口是对象向外部公开其功能的方式。 在 COM 中，接口是一个指针表， (如 c + + vtable) 对象实现的函数。 该表表示接口，它指向的函数是该接口的方法。 对象可以公开所选的任意数量的接口。

每个接口都基于基本 COM 接口 [IUnknown](../atl/iunknown.md)。 的方法 `IUnknown` 允许导航到对象公开的其他接口。

同时，为每个接口指定唯一的接口 ID (IID) 。 这种唯一性使支持接口版本控制变得轻松。 新版本的接口只是新的接口，具有新的 IID。

> [!NOTE]
> 标准 COM 和 OLE 接口的 Iid 是预定义的。

## <a name="see-also"></a>请参阅

[COM 简介](../atl/introduction-to-com.md)<br/>
[COM 对象和接口](/windows/win32/com/com-objects-and-interfaces)
