---
description: 详细了解：编译器警告 (等级 3) C4414
title: 编译器警告（等级 3）C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: c753852d40a044e99b91aa8a5976811aab52c5ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177167"
---
# <a name="compiler-warning-level-3-c4414"></a>编译器警告（等级 3）C4414

"function"：短跳转到转换为附近的函数

短跳转从指令的有限范围内生成分支到地址的精简指令。 指令包含一个短偏移量，该偏移量表示跳转与目标地址（函数定义）之间的距离。 在链接函数的过程中，可能会移动或服从链接时间优化，从而导致函数从短偏移量中可访问的范围内移出。 编译器必须为跳转生成特殊记录，这需要跳转指令接近或远远。 编译器进行了转换。

例如，下面的代码生成 C4414：

```cpp
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```
