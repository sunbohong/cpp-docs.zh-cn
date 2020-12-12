---
description: 了解更多：编译器错误 C2199
title: 编译器错误 C2199
ms.date: 11/04/2016
f1_keywords:
- C2199
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
ms.openlocfilehash: e3c1daefb8a8b14c49b42e48c0d46d5a8e638953
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278411"
---
# <a name="compiler-error-c2199"></a>编译器错误 C2199

语法错误：在全局范围内找到 "标识符 (" (是否打算使用声明？ ) 

指定的上下文导致语法错误。 可能存在不正确的声明语法。

下面的示例生成 C2199：

```cpp
// C2199.cpp
// compile with: /c
int j = int(1) int(1);   // C2199
int j = 1;   // OK
```
