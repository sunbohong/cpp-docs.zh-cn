---
description: 了解更多：编译器错误 C2529
title: 编译器错误 C2529
ms.date: 11/04/2016
f1_keywords:
- C2529
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
ms.openlocfilehash: 007fa64332e9f7b5eb993f722e66924584d9c342
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302265"
---
# <a name="compiler-error-c2529"></a>编译器错误 C2529

"name"：引用引用是非法的

可以通过使用指针语法并声明对指针的引用来解决此错误。

下面的示例生成 C2529：

```cpp
// C2529.cpp
// compile with: /c
int i;
int &ri = i;
int &(&rri) = ri;   // C2529
```
