---
description: 详细了解：编译器警告 (等级 3) C4013
title: 编译器警告 (等级 3) C4013
ms.date: 11/04/2016
f1_keywords:
- C4013
helpviewer_keywords:
- C4013
ms.assetid: 9f9afc71-6e78-463d-9d66-3012d6a3cd5d
ms.openlocfilehash: fe0da0d4a3f1b57b88cbfe148f1955d5d2fad366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173410"
---
# <a name="compiler-warning-level-3-c4013"></a>编译器警告 (等级 3) C4013

未定义 "function";假定 extern 返回 int

编译器遇到了对未定义的函数的调用。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 函数名称的拼写不正确

1. 不作为原型的外部函数 **`extern`**
