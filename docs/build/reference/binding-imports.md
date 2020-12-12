---
description: 了解详细信息：绑定导入
title: 绑定导入
ms.date: 11/04/2016
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
ms.openlocfilehash: 7d1b4374bf1d3340a918f252d80102057febe053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182705"
---
# <a name="binding-imports"></a>绑定导入

默认链接器行为是为延迟加载的 DLL 创建可绑定的导入地址表。 如果 DLL 已绑定，则 helper 函数将尝试使用绑定的信息，而不是对每个引用的导入调用 **GetProcAddress** 。 如果时间戳或首选地址与加载的 DLL 的时间戳或首选地址不匹配，则 helper 函数将假定绑定导入地址表过期，将继续执行，就像它不存在一样。

如果永远不打算绑定 DLL 的延迟加载导入，则在链接器的命令行上指定 [/delay](delay-delay-load-import-settings.md)： nobind 将阻止生成绑定导入地址表，并在映像文件中占用空间。

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
