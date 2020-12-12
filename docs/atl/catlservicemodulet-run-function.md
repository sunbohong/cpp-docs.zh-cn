---
description: 了解详细信息： CAtlServiceModuleT：： Run 函数
title: CAtlServiceModuleT：： Run 函数
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: f8bba170236138f6491c49506bccd29bc23d9dec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148338"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT：： Run 函数

`Run` 包含对 `PreMessageLoop` 、 `RunMessageLoop` 和的调用 `PostMessageLoop` 。 调用后， `PreMessageLoop` 先存储服务的线程 ID。 服务将使用此 ID 通过使用 Win32 API 函数 [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)发送 WM_QUIT 消息来自行关闭。

`PreMessageLoop` 然后调用 `InitializeSecurity` 。 默认情况下， `InitializeSecurity` 调用 [CoInitializeSecurity](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) 并将安全描述符设置为 NULL，这意味着任何用户都有权访问您的对象。

如果你不希望服务指定其自身的安全性，请重写 `PreMessageLoop` 并不要调用 `InitializeSecurity` ，然后，COM 将从注册表中确定安全设置。 配置注册表设置的一种简便方法是使用本部分后面讨论的 [dcomcnfg.exe](../atl/dcomcnfg.md) 实用程序。

指定安全性后，会向 COM 注册对象，以便新客户端可以连接到该程序。 最后，该程序会告诉服务控制管理器 (SCM) 它正在运行，并且程序进入消息循环。 在服务关闭后，程序将一直保持运行状态，直到它发布 quit 消息。

## <a name="see-also"></a>请参阅

[服务](../atl/atl-services.md)<br/>
[CSecurityDesc 类](../atl/reference/csecuritydesc-class.md)<br/>
[CSid 类](../atl/reference/csid-class.md)<br/>
[CDacl 类](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT：： Run](../atl/reference/catlservicemodulet-class.md#run)
