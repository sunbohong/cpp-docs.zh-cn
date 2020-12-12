---
description: 了解详细信息：链接器工具警告 LNK4102
title: 链接器工具警告 LNK4102
ms.date: 11/04/2016
f1_keywords:
- LNK4102
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
ms.openlocfilehash: b0977cfa89c0ddb5edbc7dc74428b774331a87e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294452"
---
# <a name="linker-tools-warning-lnk4102"></a>链接器工具警告 LNK4102

导出删除的析构函数 "name";图像可能无法正确运行

该程序已尝试导出删除的析构函数。 生成的删除可能会在 DLL 边界内发生，以便进程可以释放不拥有的内存。 请确保 .def 文件中未列出给定的符号，并且该符号未在链接器命令行中作为 **/IMPORT** 或 **/export** 选项的参数列出。

如果要重新生成 C 运行时库，可以忽略此消息。
