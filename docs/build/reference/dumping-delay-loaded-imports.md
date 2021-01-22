---
description: 了解详细信息：转储延迟加载的导入
title: 转储延迟加载的导入
ms.date: 01/19/2021
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.openlocfilehash: 6a0fec0b10bc29ea919195302334a25f71de0abd
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666909"
---
# <a name="dump-delay-loaded-imports"></a>转储延迟加载的导入

可以使用转储延迟加载的导入 [`dumpbin /imports`](imports-dumpbin.md) 。 这些导入显示的信息与标准导入略有不同。 它们被隔离到列表中其自己的部分 `/imports` ，并显式标记为延迟加载的导入。 如果映像中存在卸载信息，则说明。 如果存在绑定信息，则与导入的绑定地址一起注明目标 DLL 的时间和日期戳。

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
