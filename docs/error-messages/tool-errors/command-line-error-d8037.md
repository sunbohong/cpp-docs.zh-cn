---
description: 了解详细信息： Command-Line 错误 D8037
title: 命令行错误 D8037
ms.date: 11/04/2016
f1_keywords:
- D8037
helpviewer_keywords:
- D8037
ms.assetid: acddaaa0-bd84-426f-a37b-8f680b379c9d
ms.openlocfilehash: a3f01828bbe8d1df98260ebec2b5646442ec65e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136179"
---
# <a name="command-line-error-d8037"></a>命令行错误 D8037

无法创建临时 il 文件;清除旧 il 文件的临时目录

空间不足，无法创建临时的编译器中间文件。 若要更正此错误，请删除 **TMP** 环境变量指定的目录中的所有旧 MSIL 文件。 这些文件的格式将为 _CL_hhhhhhhh，其中 h 表示随机十六进制数字，ss 表示 IL 文件的类型。 此外，请确保用最新的操作系统修补程序更新计算机。

## <a name="see-also"></a>请参阅

[命令行错误 D8000 到 D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC 编译器选项](../../build/reference/compiler-options.md)
