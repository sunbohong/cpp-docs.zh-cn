---
description: 了解更多：编译器错误 C2781
title: 编译器错误 C2781
ms.date: 11/04/2016
f1_keywords:
- C2781
helpviewer_keywords:
- C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
ms.openlocfilehash: 9d99353b808494b20007784dd6016097afc783d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298001"
---
# <a name="compiler-error-c2781"></a>编译器错误 C2781

"声明"：应至少提供 value1 参数-value2

带有变量参数列表的函数模板的参数太少。

下面的示例生成 C2781：

```cpp
// C2781.cpp
template<typename T>
void f(T, T, ...){}

int main() {
   f(1);   // C2781

   // try the following line instead
   f(1,1);
}
```
