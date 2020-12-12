---
description: 了解更多：编译器错误 C3868
title: 编译器错误 C3868
ms.date: 11/04/2016
f1_keywords:
- C3868
helpviewer_keywords:
- C3868
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
ms.openlocfilehash: c71a5321b99e5852a2dc7267dd098bfec08c5ad2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222809"
---
# <a name="compiler-error-c3868"></a>编译器错误 C3868

"type"：泛型参数 "parameter" 的约束与声明上的约束不同

多个声明必须具有相同的泛型约束。  有关详细信息，请参阅[泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3868。

```cpp
// C3868.cpp
// compile with: /clr /c
interface struct I1;

generic <typename T> ref struct MyStruct;
generic <typename U> where U : I1 ref struct MyStruct;   // C3868

// OK
generic <typename T> ref struct MyStruct2;
generic <typename U> ref struct MyStruct2;

generic <typename T> where T : I1 ref struct MyStruct3;
generic <typename U> where U : I1 ref struct MyStruct3;
```
