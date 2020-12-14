---
description: 了解详细信息：严重错误 C1510
title: 错误 C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: 3112874f033fdeed4cc4290b2469105a275baed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276317"
---
# <a name="fatal-error-c1510"></a>错误 C1510

无法打开语言资源 clui.dll

编译器无法加载语言资源 DLL。

此问题有两个常见的原因。 使用32位编译器和工具时，对于在链接期间使用超过2GB 内存的大型项目，可能会看到此错误。 64位 Windows 系统上的一种可能的解决方案是使用64位本机或跨平台编译器和工具生成代码。 这会利用可用于64位应用的更大内存空间。 如果你必须使用32位编译器，因为你在32位系统上运行，在某些情况下，你可以将可供链接器使用的内存量增加到3GB。 有关详细信息，请参阅 [4 Gb 优化： BCDEdit and Boot.ini](/windows/win32/memory/4-gigabyte-tuning) 和 [BCDEdit/set increaseuserva](/windows-hardware/drivers/devtest/bcdedit--set) 命令。

另一个常见原因是 Visual Studio 安装已损坏或不完整。 在这种情况下，请再次运行安装程序来修复或重新安装 Visual Studio。
