---
description: 了解更多：编译器错误 C2120
title: 编译器错误 C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 064c0587275d85c3cff520075352825d17d41aef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170048"
---
# <a name="compiler-error-c2120"></a>编译器错误 C2120

"void" 对于所有类型都非法

**`void`** 类型用在具有另一种类型的声明中。

下面的示例生成 C2120：

```cpp
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
