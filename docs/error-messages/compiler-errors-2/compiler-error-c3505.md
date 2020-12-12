---
description: 了解更多：编译器错误 C3505
title: 编译器错误 C3505
ms.date: 11/04/2016
f1_keywords:
- C3505
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
ms.openlocfilehash: 10727b04ce587eb56872440ad7d46dd544eb0642
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113108"
---
# <a name="compiler-error-c3505"></a>编译器错误 C3505

> 无法加载类型库 "*guid*"

如果对64位计算机上的64位、x64 目标运行32位的 x86 托管交叉编译器，则可能会导致 C3505，这是因为编译器在 WOW64 下运行，并且只能从32位注册表配置单元中读取。

您可以通过构建您尝试导入的类型库的32位和64位版本来解决此错误，然后将它们都注册。  或者，你可以使用本机64位编译器，该编译器要求你将 IDE 中的 " **VC + + 目录** " 属性更改为指向64位编译器。

有关详细信息，请参阅

- [如何：在命令行上启用 64 位 Visual C++ 工具集](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [如何：针对 64 位 x64 平台配置 Visual C++ 项目](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)
