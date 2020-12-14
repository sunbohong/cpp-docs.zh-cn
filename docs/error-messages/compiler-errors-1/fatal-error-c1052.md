---
description: 了解详细信息：严重错误 C1052
title: 错误 C1052
ms.date: 05/08/2017
f1_keywords:
- C1052
helpviewer_keywords:
- C1052
ms.assetid: f2c09a2f-d3c1-4420-9501-ffcb65caf87b
ms.openlocfilehash: 818210cc4c3658167de30b9e666c600695389330
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251734"
---
# <a name="fatal-error-c1052"></a>错误 C1052

> 程序数据库文件 "*filename*" 是使用/debug： fastlink 的链接器生成的。编译器无法更新此类 PDB 文件;请删除它或使用/Fd 来指定不同的 PDB 文件名

指定 [/debug： fastlink](../../build/reference/debug-generate-debug-info.md) 选项时，编译器无法更新由链接器生成的同一程序数据库 (PDB) 文件。 通常，编译器生成的 PDB 文件和链接器生成的 PDB 文件具有不同的名称。 但是，如果将其设置为使用相同的名称，则会导致此错误。

若要解决此问题，可以在再次编译之前显式删除 PDB 文件，也可以为编译器生成的和由链接器生成的 PDB 文件创建不同的名称。

若要在命令行上指定编译器生成的 PDB 文件名，请使用 [/fd](../../build/reference/fd-program-database-file-name.md) 编译器选项。 若要在 IDE 中指定编译器生成的 PDB 文件名，请打开项目的 " **属性页** " 对话框，并在 " **配置属性**" " **c/c + +"-**> " **输出文件** " 页中，设置 " **程序数据库文件名** " 属性。 默认情况下，此属性为 `$(IntDir)vc$(PlatformToolsetVersion).pdb` 。

或者，可以设置链接器生成的 PDB 文件名。 若要在命令行上指定链接器生成的 PDB 文件名，请使用 [/pdb](../../build/reference/pdb-use-program-database.md) 链接器选项。 若要在 IDE 中指定链接器生成的 PDB 文件名，请打开项目的 " **属性页** " 对话框，并在 " **配置属性**"、" **链接器**"、" **调试** " 页中设置 " **生成程序数据库文件** " 属性。 默认情况下，此属性设置为 `$(OutDir)$(TargetName).pdb`。
