---
description: 详细了解绑定延迟加载的导入
title: 绑定延迟加载的导入
ms.date: 01/19/2021
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.openlocfilehash: 49d321a30eeb3ab12ec832fb86a662f2035e1e3a
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666935"
---
# <a name="bind-delay-loaded-imports"></a>绑定延迟加载的导入

默认链接器行为是为延迟加载的 DLL 创建 (IAT) 的可绑定导入地址表。 如果 DLL 是绑定的，则 helper 函数尝试使用绑定的信息，而不是 `GetProcAddress` 对每个引用的导入调用。 如果时间戳或首选地址与加载的 DLL 中的时间戳或首选地址不匹配，则 helper 函数将假定绑定导入地址表过期。 它将继续执行，就好像 IAT 不存在一样。

如果永远不打算绑定 DLL 的延迟加载导入，请 [`/delay:nobind`](delay-delay-load-import-settings.md) 在链接器命令行上指定。 链接器不会生成绑定的导入地址表，这将节省图像文件中的空间。

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
