---
description: 了解详细信息：显示断言
title: 显示断言
ms.date: 05/05/2019
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
ms.openlocfilehash: 3f925d5f3a7d1ad0ac1171ea8983b57ead147bf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153009"
---
# <a name="displaying-assertions"></a>显示断言

如果连接到服务的客户端似乎停止响应，则该服务可能已断言并显示你无法看到的消息框。 你可以通过使用 Visual Studio 调试器调试你的代码来进行确认 (参阅本部分前面的 [使用任务管理器](../atl/using-task-manager.md)) 。

如果确定服务显示的是无法看到的消息框，则可能需要将 " **允许服务与桌面交互** " 选项设置为再次使用该服务。 此选项是一个启动参数，该参数允许服务显示的任何消息框显示在桌面上。 若要设置此选项，请打开 "服务" 控制面板应用程序，选择服务，单击 " **启动**"，然后选择 " **允许服务与桌面交互** " 选项。

## <a name="see-also"></a>请参阅

[调试提示](../atl/debugging-tips.md)
