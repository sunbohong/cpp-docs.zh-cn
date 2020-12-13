---
description: 了解更多：编译器错误 C3285
title: 编译器错误 C3285
ms.date: 11/04/2016
f1_keywords:
- C3285
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
ms.openlocfilehash: d5b57b878ed47118e1857558b9d633bb5ef7286c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339327"
---
# <a name="compiler-error-c3285"></a>编译器错误 C3285

for each 语句不能对“类型”类型的变量进行操作

`for each` 语句针对数组或集合中每个元素重复执行一组嵌入语句。

有关更多信息，请参见 [for each, in](../../dotnet/for-each-in.md) 。

## <a name="example"></a>示例

以下示例生成 C3285.

```cpp
// C3285.cpp
// compile with: /clr
int main() {
   for each (int i in 0) {}   // C3285

   array<int> ^p = { 1, 2, 3 };
   for each (int j in p) {}   // OK
}
```
