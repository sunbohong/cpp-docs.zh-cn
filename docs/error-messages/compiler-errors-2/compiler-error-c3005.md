---
description: 了解更多：编译器错误 C3005
title: 编译器错误 C3005
ms.date: 11/04/2016
f1_keywords:
- C3005
helpviewer_keywords:
- C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
ms.openlocfilehash: df9e0c94aa0ba47e1c2f63858419c15881f9bd74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272416"
---
# <a name="compiler-error-c3005"></a>编译器错误 C3005

“error_text”：OpenMP“directive”指令上出现意外的标记

OpenMP 指令格式不正确。

下面的示例生成 C3005：

```c
// C3005.c
// compile with: /openmp
int main()
{
   #pragma omp parallel + for   // C3005
}
```

如果将左大括号放置在杂注所在的行，也会发生 C3005。

```c
// C3005b.c
// compile with: /openmp
int main() {
   #pragma omp parallel {   // C3005 put open brace on next line
   lbl2:;
   }
   goto lbl2;
}
```
