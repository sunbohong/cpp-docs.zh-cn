---
description: 了解更多：编译器错误 C2267
title: 编译器错误 C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: df69073cbb1956033cf7d028c56e13018e4bbcf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328407"
---
# <a name="compiler-error-c2267"></a>编译器错误 C2267

"function"：具有块范围的静态函数是非法的

声明了本地函数 **`static`** 。 静态函数必须具有全局范围。

下面的示例生成 C2267：

```cpp
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```
