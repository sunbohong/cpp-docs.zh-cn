---
description: 了解详细信息：作为本地服务器运行程序
title: 以本地服务器的形式运行程序
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: 1cdf3cef0773769318d68964b28bb60ca66666d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157486"
---
# <a name="running-the-program-as-a-local-server"></a>以本地服务器的形式运行程序

如果以服务的形式运行该程序是不方便的，则可以暂时更改注册表，以使程序作为普通的本地服务器运行。 只需将 `LocalService` AppID 下的值重命名为 `_LocalService` ，并确保 `LocalServer32` CLSID 下的密钥设置正确。  (请注意，使用 DCOMCNFG.EXE 指定应用程序应在不同的计算机上运行，则会将你的密钥重命名 `LocalServer32` 为。 ) 将你的 `_LocalServer32` 程序作为本地服务器运行将需要几秒钟的时间才能启动，因为对中的的调用在 `StartServiceCtrlDispatcher` `CAtlServiceModuleT::Start` 失败之前需要几秒钟。

## <a name="see-also"></a>请参阅

[调试提示](../atl/debugging-tips.md)
