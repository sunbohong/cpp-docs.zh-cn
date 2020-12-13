---
description: 了解详细信息：编译器警告 (等级 1) C4145
title: 编译器警告（等级 1）C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 2eaafd131e7dcfba7b94fbc84e5c2b9da2dfa89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136248"
---
# <a name="compiler-warning-level-1-c4145"></a>编译器警告（等级 1）C4145

“expression1”: 关系表达式用作 switch 表达式；可能和“expression2”混淆

**`switch`** 语句使用关系表达式作为其控制表达式，这会导致语句的布尔值 **`case`** 。 是否希望使用 *expression2*?

## <a name="example"></a>示例

下面的示例生成 C4145:

```cpp
// C4145.cpp
// compile with: /W1
int main() {
   int i = 0;
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve
      case 1:
         break;
      default:
         break;
   }
}
```
