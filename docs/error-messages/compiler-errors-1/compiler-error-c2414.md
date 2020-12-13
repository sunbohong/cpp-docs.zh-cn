---
description: 了解更多：编译器错误 C2414
title: 编译器错误 C2414
ms.date: 11/04/2016
f1_keywords:
- C2414
helpviewer_keywords:
- C2414
ms.assetid: bbe94e03-862e-4990-b15e-544ae464727d
ms.openlocfilehash: 5bf2d017ac0018fe092b5a003dee021dd13370b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340328"
---
# <a name="compiler-error-c2414"></a>编译器错误 C2414

非法的操作数数目

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 操作码不支持使用的操作数。 检查汇编语言引用手册以确定正确的操作数。

1. 较新的处理器支持具有不同数量操作数的指令。 将 [/arch (最小 CPU 体系结构) ](../../build/reference/arch-minimum-cpu-architecture.md) 选项调整为使用更高版本的处理器。
