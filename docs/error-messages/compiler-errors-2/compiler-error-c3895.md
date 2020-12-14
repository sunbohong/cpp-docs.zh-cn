---
description: 了解更多：编译器错误 C3895
title: 编译器错误 C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: ae963eb89ee8f0cefc9092e9d3b16aa40885e63c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315109"
---
# <a name="compiler-error-c3895"></a>编译器错误 C3895

"var"：类型数据成员不能是 "volatile"

某些类型的数据成员（例如 [文本](../../extensions/literal-cpp-component-extensions.md) 或 [initonly](../../dotnet/initonly-cpp-cli.md)）不能是 [可变](../../cpp/volatile-cpp.md)的。

下面的示例生成 C3895：

```cpp
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```
