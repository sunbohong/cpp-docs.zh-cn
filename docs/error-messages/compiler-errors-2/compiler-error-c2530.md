---
description: 了解更多：编译器错误 C2530
title: 编译器错误 C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 07980fb6d87b4e84bc0b253ccd317eba02fa81af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258104"
---
# <a name="compiler-error-c2530"></a>编译器错误 C2530

"identifier"：必须初始化引用

必须在声明引用后对其进行初始化（除非已声明）：

- 带有关键字 [extern](../../cpp/extern-cpp.md)。

- 作为类、结构或联合 (的成员，并在构造函数) 中对其进行初始化。

- 作为函数声明或定义中的参数。

- 作为函数的返回类型。

下面的示例生成 C2530：

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
