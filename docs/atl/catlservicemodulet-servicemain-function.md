---
description: 了解详细信息： CAtlServiceModuleT：： ServiceMain 函数
title: CAtlServiceModuleT：： ServiceMain 函数
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 97093d13a2f13ea0d6bd4ba5db46bef45d239cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148325"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT：： ServiceMain 函数

当你打开 "服务" 控制面板应用程序时，"服务控制管理器" (SCM) 调用 `ServiceMain` ，请选择该服务，然后单击 " **启动**"。

在 SCM 调用后 `ServiceMain` ，服务必须为 SCM 指定处理程序函数。 此函数可让 SCM 获取服务的状态，并传递特定说明 (例如暂停或停止) 。 当服务传递 `_Handler` 到 Win32 API 函数 [RegisterServiceCtrlHandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw)时，SCM 获取此函数。  (`_Handler` 是调用非静态成员函数 [处理程序](../atl/reference/catlservicemodulet-class.md#handler)的静态成员函数。 ) 

在启动时，服务还应通知 SCM 其当前状态。 它通过将 SERVICE_START_PENDING 传递到 Win32 API 函数 [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus)来实现此功能。

`ServiceMain` 然后调用 `CAtlExeModuleT::InitializeCom` ，它调用 Win32 API 函数 [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)。 默认情况下，会将 `InitializeCom` COINIT_MULTITHREADED 标志传递到函数。 此标志指示该程序是一个自由线程服务器。

现在， `CAtlServiceModuleT::Run` 调用以执行服务的主要工作。 `Run` 继续执行，直到服务停止。

## <a name="see-also"></a>请参阅

[服务](../atl/atl-services.md)<br/>
[CAtlServiceModuleT：： ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
