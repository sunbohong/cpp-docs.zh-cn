---
description: 了解详细信息：为提供程序启用和禁用服务
title: 为提供程序启用或禁用服务
ms.date: 07/30/2019
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: ead2ce9b8f1e678af00bcc03140c2868986a1564
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287536"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>为提供程序启用或禁用服务

默认情况下，可以为访问单个提供程序的所有应用程序启用或禁用单个 OLE DB 服务。 为此，可以在提供程序的 CLSID 下添加 OLEDB_SERVICES 注册表项，并使用 DWORD 值指定要启用或禁用的服务，如下表所示。

|已启用默认服务|DWORD 值|
|------------------------------|-------------------|
|除客户端游标和池外的所有服务|0xfffffffa|
|除客户端游标外的所有服务|0xfffffffb|
|除池和自动登记之外的所有服务|0xfffffffc|
|除池之外的所有服务|0xfffffffe|
|所有服务 (默认值) |0xffffffff|
|无服务|0x00000000|
|没有聚合，禁用了所有服务|无 OLEDB_Services 注册表项|

## <a name="see-also"></a>请参阅

[启用和禁用 OLE DB 服务](../../data/oledb/enabling-and-disabling-ole-db-services.md)
