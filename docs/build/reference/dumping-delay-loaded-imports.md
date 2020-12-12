---
description: 了解详细信息：转储 Delay-Loaded 导入
title: 转储延迟加载的导入
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: c57ff6bb4a3dce16b4cb1eb85fdffff4ef272396
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201074"
---
# <a name="dumping-delay-loaded-imports"></a>转储延迟加载的导入

可以使用 [dumpbin/imports](imports-dumpbin.md) 转储延迟加载的导入，并显示与标准导入略有不同的信息。 它们被隔离到/imports 转储的各自部分，并显式标记为延迟加载的导入。 如果图像中存在卸载信息，则注明。 如果存在绑定信息，将与导入的绑定地址一起注明目标 DLL 的时间/日期戳。

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
