---
description: 了解更多：编译器错误 C3001
title: 编译器错误 C3001
ms.date: 11/04/2016
f1_keywords:
- C3001
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
ms.openlocfilehash: cf8acec3fb95553787e14968b9ce3e608da83916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253593"
---
# <a name="compiler-error-c3001"></a>编译器错误 C3001

“error_text”: 应为 OpenMP 指令名称

`omp` 杂注后面必须跟有指令。

下面的示例生成 C3001：

```c
// C3001.c
// compile with: /openmp
int main()
{
   #pragma omp   // C3001 missing token
}
```
