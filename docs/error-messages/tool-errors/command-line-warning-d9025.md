---
description: 了解详细信息： Command-Line 警告 D9025
title: 命令行警告 D9025
ms.date: 11/04/2016
f1_keywords:
- D9025
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
ms.openlocfilehash: 8cec7bdb5f3816c33d395e8ae93a861a29e94c64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115490"
---
# <a name="command-line-warning-d9025"></a>命令行警告 D9025

重写 "选项 1" 和 "选项 2"

已指定 *选项 1* 选项，但已被 *选项 2* 重写。 使用了 *选项 2* 选项。

如果两个选项指定了矛盾或不兼容的指令，则使用命令行右侧最远的选项中指定或隐含的指令。

如果在从开发环境中进行编译时收到此警告，并不确定冲突选项来自何处，请注意以下事项：

- 可以在代码或项目的项目设置中指定一个选项。 如果查看编译器的 " [命令行" 属性页](../../build/reference/command-line-property-pages.md) ，并且在 " **所有选项** " 字段中看到冲突的选项，则会在项目的属性页中设置这些选项，否则将在源代码中设置这些选项。

   如果在项目的属性页中设置这些选项，请查看编译器的预处理器属性页 (在解决方案资源管理器) 中选择的项目节点。  如果看不到 "设置" 选项，请检查每个源代码文件的 "预处理器属性页设置" (解决方案资源管理器) ，以确保不会将其添加到其中。

   如果在代码中设置这些选项，则可以在代码或 windows 标头中设置这些选项。  你可以尝试创建一个预处理文件 ([/p](../../build/reference/p-preprocess-to-a-file.md)) 并在其上搜索符号。
