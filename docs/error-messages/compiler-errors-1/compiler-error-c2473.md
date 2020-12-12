---
description: 了解更多：编译器错误 C2473
title: 编译器错误 C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: c81e1329e17c03b3bd8f857d2f8ceddcc1a9f264
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164453"
---
# <a name="compiler-error-c2473"></a>编译器错误 C2473

“identifier”: 看起来像函数定义，但却没有参数列表。

编译器检测到看似为函数、但没有参数列表的内容。

## <a name="example"></a>示例

下面的示例生成 C2473。

```cpp
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```
