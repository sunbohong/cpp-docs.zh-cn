---
description: 了解更多：编译器错误 C3391
title: 编译器错误 C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: 1bac535136b2c6115bf0f5ff31c9e098407e03bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313393"
---
# <a name="compiler-error-c3391"></a>编译器错误 C3391

"type_arg"：泛型 "generic_type" 的泛型参数 "param" 的类型参数无效，它必须是不可以为 null 的值类型

泛型类型实例化错误。 检查类型定义。 有关详细信息，请参阅 <xref:System.Nullable> 和 [泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例使用 c # 创建一个包含泛型类型的组件，该泛型类型具有在 c + +/CLI 中创作泛型类型时不受支持的某些约束。 有关详细信息，请参阅[类型参数的约束](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)。

```csharp
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

当 C3391.dll 组件可用时，以下示例生成 C3391。

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```
