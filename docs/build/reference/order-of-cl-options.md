---
description: 了解详细信息： CL 选项的顺序
title: " (c + +) 的 CL 选项的顺序-Visual Studio"
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: bc0290164ff40cf45d8d0a1e9f07e683e408c251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226410"
---
# <a name="order-of-cl-options"></a>CL 选项的顺序

选项可以出现在 CL 命令行中的任何位置，但/link 选项除外，后者必须最后发生。 编译器以 [CL 环境变量](cl-environment-variables.md) 中指定的选项开始，然后从左到右读取命令行（按照其遇到的顺序处理命令文件）。 每个选项都适用于命令行上的所有文件。 如果 CL 遇到冲突的选项，它将使用最右侧的选项。

## <a name="see-also"></a>请参阅

[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
