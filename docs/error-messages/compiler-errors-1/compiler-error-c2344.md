---
description: 了解更多：编译器错误 C2344
title: 编译器错误 C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: 1ad4f1808f407a9f654f5bbf3a022c2dc7b0b3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234756"
---
# <a name="compiler-error-c2344"></a>编译器错误 C2344

align(#)：对齐必须是 2 的幂

当使用 [align](../../cpp/align-cpp.md) 关键字时，传递的值必须是 2 的幂。

例如，下面的代码生成 C2344，因为 3 不是 2 的幂：

```cpp
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```
