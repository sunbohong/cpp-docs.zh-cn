---
description: 详细了解：编译器警告 (级别 4) C4221
title: 编译器警告（等级 4）C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: 4632b075dfb6a7c1895415a253c70f5b4fd4f278
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164271"
---
# <a name="compiler-warning-level-4-c4221"></a>编译器警告（等级 4）C4221

使用了非标准扩展： "identifier"：无法使用自动变量的地址初始化

使用默认的 Microsoft 扩展 (/Ze) ，你可以 **`struct`** **`union`** 使用本地 (自动) 变量的地址初始化 (数组、或) 的聚合类型。

## <a name="example"></a>示例

```c
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

此类初始化在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中无效。
