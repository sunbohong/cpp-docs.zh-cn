---
description: 了解更多：编译器错误 C2333
title: 编译器错误 C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: 6db3e68dd9a709abbb8153ad8b4acdaf7d4d6f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234886"
---
# <a name="compiler-error-c2333"></a>编译器错误 C2333

"function"：函数声明中有错误;跳过函数体

对于在其类中定义的成员函数，出现其他错误后，将出现此错误。

下面的示例生成 C2333：

```cpp
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```
