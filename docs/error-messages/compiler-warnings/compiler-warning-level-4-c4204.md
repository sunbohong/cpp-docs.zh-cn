---
description: 详细了解：编译器警告 (级别 4) C4204
title: 编译器警告（等级 4）C4204
ms.date: 11/04/2016
f1_keywords:
- C4204
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
ms.openlocfilehash: edb802e1aa958e28d0a41f3cc64f5ddf058db909
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314784"
---
# <a name="compiler-warning-level-4-c4204"></a>编译器警告（等级 4）C4204

使用了非标准扩展：非常量聚合初始值设定项

利用 Microsoft extension (/Ze) ，你可以 (数组、结构、联合和类) 值不是常量的值来初始化聚合类型。

## <a name="example"></a>示例

```c
// C4204.c
// compile with: /W4
int func1()
{
   return 0;
}
struct S1
{
   int i;
};

int main()
{
   struct S1 s1 = { func1() };   // C4204
   return s1.i;
}
```

此类初始化在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中无效。
