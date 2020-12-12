---
description: 了解详细信息：链接器工具错误 LNK1241
title: 链接器工具错误 LNK1241
ms.date: 11/04/2016
f1_keywords:
- LNK1241
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
ms.openlocfilehash: abc72b70af9ab694744a91a8789207055bd1a5bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193924"
---
# <a name="linker-tools-error-lnk1241"></a>链接器工具错误 LNK1241

已指定资源文件 "resource file"

如果从命令行手动运行 **cvtres** ，然后将生成的 .obj 文件传递给链接器以及其他 res 文件，则会生成此错误。

若要指定多个 .res 文件，请将它们全部作为 .res 文件传递给链接器，而不是从 **cvtres** 创建的 .obj 文件中传递。
