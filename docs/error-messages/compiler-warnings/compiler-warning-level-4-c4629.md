---
description: 详细了解：编译器警告 (级别 4) C4629
title: 编译器警告（等级 4）C4629
ms.date: 11/04/2016
f1_keywords:
- C4629
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
ms.openlocfilehash: b357b72ca95682c33d3f4019d4663593c5c5ee8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134168"
---
# <a name="compiler-warning-level-4-c4629"></a>编译器警告（等级 4）C4629

使用了有向图，字符序列“digraph”解释为标记“char”（如果这不是你想要的，请在这两个字符之间插入一个空格）

在 [/Za](../../build/reference/za-ze-disable-language-extensions.md)下，当编译器检测到有向图时会发出警告。

以下示例生成 C4629：

```cpp
// C4629.cpp
// compile with: /Za /W4
int main()
<%   // C4629 <% digraph for {
}
```
