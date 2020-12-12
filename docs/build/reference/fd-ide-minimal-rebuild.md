---
description: '详细了解：/FD (IDE 最小重新生成) '
title: /FD（IDE 最小重新生成）
ms.date: 04/08/2019
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: d9b2a91c14b80890c703b8f4dd5b2de3aefb012b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192286"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD（IDE 最小重新生成）

在 c + + 项目的 "**属性页**" 对话框的 "[命令行](command-line-property-pages.md)" 属性页中， **/fd** 仅向用户公开。 当且仅当不推荐使用和非默认的 [/gm (启用最小重新生成) ](gm-enable-minimal-rebuild.md) 选项时，它才可用。 **/Fd** 除了从开发环境中没有任何影响。 **/Fd** 在的输出中未公开 `cl /?` 。

如果未在开发环境中启用弃用的 **/gm** 选项，则使用 **/fd** 。 **/Fd** 确保 .idb 文件具有足够的依赖项信息。 **/Fd** 仅供开发环境使用，不应从命令行或生成脚本中使用。

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
