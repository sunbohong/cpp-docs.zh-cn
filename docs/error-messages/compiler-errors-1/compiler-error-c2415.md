---
description: 了解更多：编译器错误 C2415
title: 编译器错误 C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: 21bbeabe0a5eacea55d2a38ab515429e6468ba57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340341"
---
# <a name="compiler-error-c2415"></a>编译器错误 C2415

不正确的操作数类型

操作码不使用此类型的操作数。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 操作码不支持使用的操作数。 检查汇编语言引用手册以确定正确的操作数。

1. 较新的处理器支持使用其他类型的指令。 将 [/arch (最小 CPU 体系结构) ](../../build/reference/arch-minimum-cpu-architecture.md) 选项调整为使用更高版本的处理器。
