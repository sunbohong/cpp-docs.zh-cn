---
description: 详细了解：编译器警告 (等级 2) C4285
title: 编译器警告（等级 2）C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 2eafb9bb17c5e6ea782ff00900c410727b3b39f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173579"
---
# <a name="compiler-warning-level-2-c4285"></a>编译器警告（等级 2）C4285

如果使用中缀表示法应用，则 "identifier：： operator->" 的返回类型为递归

指定的 **> ( # B1** 函数无法返回为其定义的类型或对其定义的类型的引用。

下面的示例生成 C4285：

```cpp
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```
