---
description: 详细了解：编译器警告 (等级 3) C4622
title: 编译器警告（等级 3）C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: aa7ca3f2b31f369e40b5344e008655b84b13cd1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244805"
---
# <a name="compiler-warning-level-3-c4622"></a>编译器警告（等级 3）C4622

覆盖创建对象文件的预编译头期间生成的调试信息：“file”

当使用 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) （使用预编译头）选项编译时，指定文件中的 CodeView 信息丢失。

当创建或使用预编译头文件时（使用 [/Fo](../../build/reference/fo-object-file-name.md)）重命名对象文件，并使用新对象文件进行链接。
