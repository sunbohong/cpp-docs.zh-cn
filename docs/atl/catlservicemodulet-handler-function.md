---
description: 了解详细信息： CAtlServiceModuleT：： Handler 函数
title: CAtlServiceModuleT：： Handler 函数
ms.date: 11/04/2016
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: 934c612b6fdfd47bb9966536cc335da58fbd38c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148364"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT：： Handler 函数

`CAtlServiceModuleT::Handler` 服务控制管理器 (SCM) 调用来检索服务的状态，并向其授予各种说明 (如停止或暂停) 。 SCM 向传递一个操作代码，以 `Handler` 指示服务应执行的操作。 默认的 ATL 生成的服务仅处理停止指令。 如果 SCM 传递了 stop 指令，则该服务会告诉 SCM，程序即将停止。 然后，服务会调用 `PostThreadMessage` 向其自身发送 quit 消息。 这将终止消息循环，并最终关闭服务。

若要处理更多说明，需要更改 `m_status` 在构造函数中初始化的数据成员 `CAtlServiceModuleT` 。 此数据成员通知 SCM 当在 "服务" 控制面板应用程序中选择了服务时要启用哪些按钮。

## <a name="see-also"></a>请参阅

[服务](../atl/atl-services.md)<br/>
[CAtlServiceModuleT：： Handler](../atl/reference/catlservicemodulet-class.md#handler)
