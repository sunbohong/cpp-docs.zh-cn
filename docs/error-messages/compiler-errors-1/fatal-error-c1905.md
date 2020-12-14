---
description: 了解详细信息：严重错误 C1905
title: 错误 C1905
ms.date: 11/04/2016
f1_keywords:
- C1905
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
ms.openlocfilehash: 573f4b1b196bf748a2359271401c68e60a3d4b53
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276044"
---
# <a name="fatal-error-c1905"></a>错误 C1905

前端和后端不兼容（必须面向同一处理器）

如果一个 .obj 文件是由编译器前端 ( # A0) 生成的，而该文件以一个处理器（如 x86、ARM 或 x64）为目标，但它由面向不同处理器的后端 ( # A1) 读取，则会出现此错误。

若要解决此问题，请确保你使用的前端和后端相匹配。 对于 Visual Studio 中创建的项目，这是默认的。 如果已编辑该项目文件并使用通向编译器工具的不同路径，则可能会出现此错误。 如果未特别设置编译器工具的路径，则你的 Visual Studio 安装损坏时可能发生此错误。 例如，你可能已将编译器 .dll 文件从一个位置复制到另一个位置。 使用 Windows 控制面板中的 " **程序和功能** " 修复或重新安装 Visual Studio。
