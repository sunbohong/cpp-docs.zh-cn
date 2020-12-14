---
description: 详细了解：编译器警告 (等级 3) C4554
title: 编译器警告（等级 3）C4554
ms.date: 11/04/2016
f1_keywords:
- C4554
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
ms.openlocfilehash: daed8757cca5c9d9286f6f6bf94c55149c1687c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257831"
---
# <a name="compiler-warning-level-3-c4554"></a>编译器警告（等级 3）C4554

"operator"：检查运算符优先级是否有可能的错误;使用括号阐明优先级

下面的示例生成 C4554：

```cpp
// C4554.cpp
// compile with: /W3 /WX
int main() {
   int a = 0, b = 0, c = 0;
   a = a << b + c;   // C4554
   // probably intended (a << b) + c,
   // but will get a << (b + c)
}
```
