---
description: 详细了解：编译器警告 (等级 2) C4244
title: 编译器警告（等级 2）C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: b51af5179c9afbf01529f545bbc602ac9c9fac6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238123"
---
# <a name="compiler-warning-level-2-c4244"></a>编译器警告（等级 2）C4244

"argument"：从 "type1" 转换到 "type2"，可能丢失数据

浮点类型已转换为整数类型。  可能发生了数据丢失。

如果收到 C4244，则应将程序更改为使用兼容类型，或向代码添加一些逻辑，以确保可能值的范围将始终与你使用的类型兼容。

C4244 也可以在第3级和第4级激发;有关详细信息，请参阅 [编译器警告 (等级3和 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) 。

## <a name="example"></a>示例

下面的示例生成 C4244：

```cpp
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```
