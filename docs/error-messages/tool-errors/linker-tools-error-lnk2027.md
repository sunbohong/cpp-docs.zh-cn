---
description: 了解详细信息：链接器工具错误 LNK2027
title: 链接器工具错误 LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: 006ca3b0c9d0ef85f118db9b562e8228c7cad238
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275758"
---
# <a name="linker-tools-error-lnk2027"></a>链接器工具错误 LNK2027

无法解析的模块引用 "module"

传递给链接器的文件依赖于既不使用 **/ASSEMBLYMODULE** 指定的模块，也不直接传递到链接器。

若要解析 LNK2027，请执行以下操作之一：

- 不要向链接器传递具有模块依赖项的文件。

- 指定带有 **/ASSEMBLYMODULE** 的模块。

- 如果该模块是安全的 .netmodule，则将它直接传递给链接器。

有关详细信息，请参阅 [/ASSEMBLYMODULE (将 MSIL 模块添加到程序集) ](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) 和 [.Netmodule 文件作为链接器输入](../../build/reference/netmodule-files-as-linker-input.md)。
