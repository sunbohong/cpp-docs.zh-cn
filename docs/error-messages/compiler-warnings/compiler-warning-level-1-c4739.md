---
description: 了解详细信息：编译器警告 (等级 1) C4739
title: 编译器警告（等级 1）C4739
ms.date: 11/04/2016
f1_keywords:
- C4739
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
ms.openlocfilehash: 03473c8bb5434e8ee05778f40c2cf773de1b64da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228542"
---
# <a name="compiler-warning-level-1-c4739"></a>编译器警告（等级 1）C4739

对变量“var”的引用超过了其存储空间

将值赋给了变量，但是该值的大小超过变量的大小。 内存将写入变量的内存位置之外，并且可能丢失数据。

要消除此警告，仅需将值赋给其大小可容纳该值的变量。

下面的示例生成 C4739：

```cpp
// C4739.cpp
// compile with: /RTCs /Zi /W1 /c
char *pc;
int main() {
   char c;
   *(int *)&c = 1;   // C4739

   // OK
   *(char *)&c = 1;
}
```
