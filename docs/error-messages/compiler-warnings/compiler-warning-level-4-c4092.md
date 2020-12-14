---
description: 详细了解：编译器警告 (级别 4) C4092
title: 编译器警告 (等级 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: 70b2d94304863610ede64a30bcb1bb6d407f2e12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262005"
---
# <a name="compiler-warning-level-4-c4092"></a>编译器警告 (等级 4) C4092

> sizeof 返回 "无符号长"

运算符的操作数 **`sizeof`** 非常大，因此 **`sizeof`** 返回了 **`unsigned long`** 。 此警告出现在 Microsoft 扩展 ([`/Ze`](../../build/reference/za-ze-disable-language-extensions.md)) 下。 在 ANSI 兼容性 (**`/Za`**) 下，结果将被截断。
