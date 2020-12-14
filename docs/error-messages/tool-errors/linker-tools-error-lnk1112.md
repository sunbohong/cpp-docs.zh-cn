---
description: 了解详细信息：链接器工具错误 LNK1112
title: 链接器工具错误 LNK1112
ms.date: 11/04/2016
f1_keywords:
- LNK1112
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
ms.openlocfilehash: ba0a34e07b0806f251c0b1237dc28ab5f8becbf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281374"
---
# <a name="linker-tools-error-lnk1112"></a>链接器工具错误 LNK1112

> 模块计算机类型 "*type1*" 与目标计算机类型 "*type2*" 冲突

## <a name="remarks"></a>备注

指定为输入的对象文件为不同的计算机类型进行了编译。

例如，如果你尝试链接使用 **/clr** 编译的对象文件和使用 **/clr:pure** （计算机类型 CEE）编译的对象文件，则链接器将生成错误 LNK1112。 **/Clr： pure** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

同样，如果您通过 x64 编译器创建一个模块，并通过 x86 编译器创建另一个模块，然后尝试链接它们，则链接器将生成 LNK1112。

此错误的可能原因是你正在开发 64 位应用程序但未安装其中一个 Visual C++ 64 位编译器。 在这种情况下，64 位配置将不可用。 若要解决此问题，运行 Visual Studio 的安装程序并安装缺少的 C++ 组件。

如果在 **Configuration Manager** 中更改 **活动解决方案配置**，然后在删除中间项目文件之前尝试生成项目，也会发生此错误。 若要解决此错误，请从 "**生成**" 菜单中选择 "**重新生成解决方案**"。 还可从 "**生成**" 菜单中选择 "**清理解决方案**"，然后生成解决方案。

## <a name="see-also"></a>请参阅

- [链接器工具错误和警告](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
