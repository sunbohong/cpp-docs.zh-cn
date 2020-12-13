---
description: 了解详细信息：编译器警告 (等级 1) C4600
title: 编译器警告（等级 1）C4600
ms.date: 11/04/2016
f1_keywords:
- C4600
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
ms.openlocfilehash: d09aff9137647543cd3e71c0fa1794b37fac83f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341771"
---
# <a name="compiler-warning-level-1-c4600"></a>编译器警告（等级 1）C4600

\#pragma "macro name"：应为有效的非空字符串

当使用 [pop_macro](../../preprocessor/pop-macro.md) 或 [push_macro](../../preprocessor/push-macro.md)推送或弹出宏名称时，不能指定空字符串。

下面的示例生成 C4600：

```cpp
// C4600.cpp
// compile with: /W1
int main()
{
   #pragma push_macro("")   // C4600 passing an empty string
}
```
