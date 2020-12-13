---
description: 了解更多：编译器错误 C2459
title: 编译器错误 C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: 35cd97b93a7095aedc0015e2e7d9910172425263
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341862"
---
# <a name="compiler-error-c2459"></a>编译器错误 C2459

正在定义 "identifier"：。无法作为匿名成员添加

类、结构或联合由匿名联合的成员在其自身的范围内重新定义。

下面的示例生成 C2459：

```cpp
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```
