---
description: 了解有关以下内容的详细信息：创建。.Sbr 文件
title: 创建 .Sbr 文件
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 7f3e056418fe1716dc0130330b09c369e9bdceff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196914"
---
# <a name="creating-an-sbr-file"></a>创建 .Sbr 文件

> [!WARNING]
> 虽然安装 Visual Studio 时仍会安装 BSCMAKE，但 IDE 将不再使用它。 从 Visual Studio 2008 起，浏览信息和符号信息自动存储在解决方案文件夹的 SQL Server .sdf 文件中。

BSCMAKE 的输入文件为 .sbr 文件。 编译器) 编译的每个对象文件 ( 创建一个 .sbr 文件。 生成或更新浏览信息文件时，项目中的所有 .sbr 文件都必须在磁盘上可用。

若要创建包含所有可能信息的 .sbr 文件，请指定 [/fr](fr-fr-create-dot-sbr-file.md)。

若要创建不包含本地符号的 .sbr 文件，请指定 [/fr](fr-fr-create-dot-sbr-file.md)。 如果 .sbr 文件包含本地符号，你仍可以使用 BSCMAKE 的[/El 选项](bscmake-options.md)从 .bsc 文件中省略它们`.`

您可以创建 .sbr 文件而不执行完整编译。 例如，可以将/Zs 选项指定给编译器以执行语法检查，并在指定/FR 或/Fr. 时仍生成 .sbr 文件

如果首先将 .sbr 文件打包以删除未引用的定义，则生成过程的效率可能更高。 编译器会自动将 .sbr 文件打包。

## <a name="see-also"></a>请参阅

[生成。.Bsc 文件](building-a-dot-bsc-file.md)
