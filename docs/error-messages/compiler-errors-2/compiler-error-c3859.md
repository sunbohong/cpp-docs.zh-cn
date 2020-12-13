---
description: 了解更多：编译器错误 C3859
title: C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 25c05425072cda6924d90f08c9aeff7446a4e85b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336113"
---
# <a name="compiler-error-c3859"></a>C3859

> 超出了 PCH 的虚拟内存范围;请使用 "-Zm *值*" 或更大的命令行选项重新编译

为预编译标头分配的虚拟内存对于编译器尝试放入其中的数据量而言太小。 从 Visual Studio 2015 开始， **/zm** 建议仅在使用指令时才有意义 `#pragma hdrstop` 。 在其他情况下，它是一个虚假错误，用于指示 Windows 虚拟内存压力问题。

如果预编译标头使用 `#pragma hdrstop` 指令，请使用 **/zm** 编译器标志为预编译标头文件指定更大的值。 否则，请考虑在生成中减少并行编译进程的数目。 有关详细信息，请参阅 [/zm (指定预编译头内存分配限制) ](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)。
