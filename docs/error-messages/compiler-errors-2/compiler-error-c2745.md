---
description: 了解更多：编译器错误 C2745
title: 编译器错误 C2745
ms.date: 11/04/2016
f1_keywords:
- C2745
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
ms.openlocfilehash: 3f80ce1c13e8f1beeaa241e0638dfc9de784c3fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123027"
---
# <a name="compiler-error-c2745"></a>编译器错误 C2745

"token"：此标记不能转换为标识符

标识符必须包含合法字符。

下面的示例生成 C2745：

```cpp
// C2745.cpp
// compile with: /clr
int main() {
   int __identifier([));   // C2745
}
```
