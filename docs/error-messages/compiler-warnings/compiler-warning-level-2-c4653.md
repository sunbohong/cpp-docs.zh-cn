---
description: 详细了解：编译器警告 (等级 2) C4653
title: 编译器警告（等级 2）C4653
ms.date: 11/04/2016
f1_keywords:
- C4653
helpviewer_keywords:
- C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
ms.openlocfilehash: bf7b2e453d4f9ea90f8b0c187fa834938de15f5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173488"
---
# <a name="compiler-warning-level-2-c4653"></a>编译器警告（等级 2）C4653

编译器选项 "option" 与预编译头不一致;已忽略当前命令行选项

使用 "使用预编译头 ([/yu](../../build/reference/yu-use-precompiled-header-file.md)) " 选项指定的选项与创建预编译标头时指定的选项不一致。 此编译使用创建预编译标头时指定的选项。

当编译预编译头期间指定 ([/Zp](../../build/reference/zp-struct-member-alignment.md)) 的包结构选项的不同值时，会出现此警告。
