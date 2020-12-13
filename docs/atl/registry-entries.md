---
description: 了解更多：注册表项
title: ATL)  (注册表项
ms.date: 11/04/2016
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
ms.openlocfilehash: c89c8f64a91c09f16333c3381a33d792332543d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138575"
---
# <a name="registry-entries"></a>注册表项

DCOM 引入了应用程序 Id (Appid) 的概念，该方法将一个或多个 DCOM 对象的配置选项分组到注册表中的一个集中位置。 您可以通过在对象的 CLSID 下的名为的 "AppID" 中指示其值来指定 AppID。

默认情况下，ATL 生成的服务使用其 CLSID 作为其 AppID 的 GUID。 在下 `HKEY_CLASSES_ROOT\AppID` ，可以指定特定于 DCOM 的条目。 最初，有两个条目：

- `LocalService`，其值等于服务的名称。 如果此值存在，则使用它而不是 `LocalServer32` CLSID 下的键。

- `ServiceParameters`，其值等于 `-Service` 。 此值指定将在服务启动时传递给服务的参数。 请注意，这些参数传递给服务的 `ServiceMain` 函数，而不是 `WinMain` 。

任何 DCOM 服务还需要在下创建另一个密钥 `HKEY_CLASSES_ROOT\AppID` 。 此密钥等于 EXE 的名称并充当交叉引用，因为它包含一个指向 AppID 条目的 AppID 值。

## <a name="see-also"></a>请参阅

[服务](../atl/atl-services.md)
