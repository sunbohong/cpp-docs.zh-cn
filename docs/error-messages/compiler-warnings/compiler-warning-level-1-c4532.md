---
description: 了解详细信息：编译器警告 (等级 1) C4532
title: 编译器警告（等级 1）C4532
ms.date: 11/04/2016
f1_keywords:
- C4532
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
ms.openlocfilehash: 9468ca1242397289c832fec28d71cf245c6c8a5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294803"
---
# <a name="compiler-warning-level-1-c4532"></a>编译器警告（等级 1）C4532

"continue"：在终止处理期间跳出 __finally/finally 块具有未定义的行为

编译器遇到以下关键字之一：

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

导致在异常终止期间跳出 [__finally](../../cpp/try-finally-statement.md) 或 [finally](../../dotnet/finally.md) 块。

如果发生了异常，并且在终止处理程序的执行过程中在终止处理程序期间展开堆栈 (**`__finally`** 或 finally 块) ，并且代码在 **`__finally`** **`__finally`** 块结束之前跳出，则该行为是不确定的。 控件不能返回到展开代码，因此异常可能不会得到正确处理。

如果必须跳出某个 **`__finally`** 块，请首先检查异常终止。

下面的示例生成 C4532;只需注释掉跳转语句即可解决警告。

```cpp
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```
