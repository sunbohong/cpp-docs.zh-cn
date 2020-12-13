---
description: 详细了解：编译器警告 (等级 2) C4309
title: 编译器警告（等级 2）C4309
ms.date: 11/04/2016
f1_keywords:
- C4309
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
ms.openlocfilehash: 8ae49967078f8569a7830c2a2e2ce61f9d25e20d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339176"
---
# <a name="compiler-warning-level-2-c4309"></a>编译器警告（等级 2）C4309

"转换"：对常量值的截断

类型转换导致常数超出为其分配的空间。 可能需要对常数使用较大的类型。

下面的示例生成 C4309：

```cpp
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```
