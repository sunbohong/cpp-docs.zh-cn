---
description: 了解更多：编译器错误 C3898
title: 编译器错误 C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 4b51683b13fa9328475ba09473ef1cae5663b009
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238955"
---
# <a name="compiler-error-c3898"></a>编译器错误 C3898

"var"：类型数据成员只能是托管类型的成员

在本机类中声明了 [initonly](../../dotnet/initonly-cpp-cli.md) 数据成员。  **`initonly`** 数据成员仅可在 CLR 类中声明。

下面的示例生成 C3898：

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

可能的解决方法：

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
