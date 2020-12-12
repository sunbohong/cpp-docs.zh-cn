---
description: 了解更多：编译器错误 C3003
title: 编译器错误 C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 1bed98ebd9e0a383700583e1e23e0a977cb6e3fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326038"
---
# <a name="compiler-error-c3003"></a>编译器错误 C3003

“directive”：在指令子句之后不允许使用 OpenMP 指令名称

OpenMP 指令名称不能位于 OpenMP 指令子句之后。

下面的示例生成 C3003：

```c
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```
