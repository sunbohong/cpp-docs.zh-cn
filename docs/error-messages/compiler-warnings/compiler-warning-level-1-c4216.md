---
description: 了解详细信息：编译器警告 (等级 1) C4216
title: 编译器警告（等级 1）C4216
ms.date: 11/04/2016
f1_keywords:
- C4216
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
ms.openlocfilehash: b570863653ea64d159cbb2f4a11138b2361ce149
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266476"
---
# <a name="compiler-warning-level-1-c4216"></a>编译器警告（等级 1）C4216

使用了非标准扩展：长浮点

默认的 Microsoft extension (/Ze) 将 **float long** 视为 **`double`** 。 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 。 用于 **`double`** 维护兼容性。 下面的示例生成 C4216：

```cpp
// C4216.cpp
// compile with: /W1
float long a;   // C4216

// use the line below to resolve the warning
// double a;

int main() {
}
```
