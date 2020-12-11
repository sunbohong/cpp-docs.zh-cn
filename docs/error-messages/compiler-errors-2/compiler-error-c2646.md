---
description: 了解更多：编译器错误 C2646
title: 编译器错误 C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: 7aa378a0a2dbaeae78a63f97e83a84d94d861c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160813"
---
# <a name="compiler-error-c2646"></a>编译器错误 C2646

全局或命名空间范围的匿名结构或联合必须声明为静态

匿名结构或联合具有全局或命名空间范围，但未声明 **`static`** 。

下面的示例生成 C2646，并演示如何修复此错误：

```cpp
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```
