---
description: 了解详细信息：链接器工具警告 LNK4070
title: 链接器工具警告 LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 188c8d88fa4fec332dad80fd5afee346f6099fca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210174"
---
# <a name="linker-tools-warning-lnk4070"></a>链接器工具警告 LNK4070

/OUT：中的 filename 指令。EXP 不同于输出文件名 "filename";正在忽略指令

`filename`当创建 .exp 文件时，在[名称](../../build/reference/name-c-cpp.md)或[库](../../build/reference/library.md)语句中指定的不是 `filename` 默认情况下或使用[/out](../../build/reference/out-output-file-name.md)选项指定的输出。

如果在开发环境中更改了输出文件的名称，但未更新项目的 .def 文件，则会看到此警告。 手动更新 .def 文件以解决此警告。

使用生成的 DLL 的客户端程序可能会遇到问题。
