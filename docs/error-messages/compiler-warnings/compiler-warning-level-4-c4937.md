---
description: 详细了解：编译器警告 (级别 4) C4937
title: 编译器警告（等级 4）C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: fa614e9f93cf83afbe3ff46e624f13b5199a28d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251240"
---
# <a name="compiler-warning-level-4-c4937"></a>编译器警告（等级 4）C4937

“text1”和“text2”作为“directive”的参数时不可区分

由于编译器处理指令的参数的方式不同，无法区分对编译器具有意义的名称，如具有多文本表现形式（单下划线或双下划线形式）的关键字。

此类字符串的示例 __cdecl 和 \_ _forceinline。  请注意，在 /Za 下，仅双下划线形式有效。

下面的示例生成 C4937：

```cpp
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```
