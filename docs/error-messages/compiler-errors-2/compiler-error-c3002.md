---
description: 了解更多：编译器错误 C3002
title: 编译器错误 C3002
ms.date: 11/04/2016
f1_keywords:
- C3002
helpviewer_keywords:
- C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
ms.openlocfilehash: 00984b6d3ed0845dd532f82462d9c44f6893a846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326051"
---
# <a name="compiler-error-c3002"></a>编译器错误 C3002

“name1 name2”：多个 OpenMP 指令名称

不允许使用多个指令名称。

下面的示例生成 C3002：

```c
// C3002.c
// compile with: /openmp
int main()
{
   #pragma omp parallel single   // C3002
}
```
