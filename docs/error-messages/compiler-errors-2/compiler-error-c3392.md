---
description: 了解更多：编译器错误 C3392
title: 编译器错误 C3392
ms.date: 11/04/2016
f1_keywords:
- C3392
helpviewer_keywords:
- C3392
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
ms.openlocfilehash: c64b49bee05079fd2d1b468d807af5b1fd89ba26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316331"
---
# <a name="compiler-error-c3392"></a>编译器错误 C3392

“type_arg”: 对于泛型“generic_type”，泛型参数“param”的类型变量无效，它必须具有公共无参数构造函数

泛型类型实例化错误。 检查类型定义。 有关详细信息，请参阅  [泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例使用 c # 创建一个包含泛型类型的组件，该泛型类型具有在 c + +/CLI 中创作泛型类型时不受支持的某些约束。 有关详细信息，请参阅[类型参数的约束](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)。

```csharp
// C3392.cs
// Compile by using: csc /target:library C3392.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

当 C3392.dll 组件可用时，以下示例生成 C3392。

```cpp
// C3392_b.cpp
// Compile by using: cl /clr C3392_b.cpp
#using <C3392.dll>

ref class R { R(int) {} };
ref class N { N() {} };

value class V {};

ref class N2 { public: N2() {} };
ref class R2 { public: R2() {} };

int main () {
   GR<R^, V, N^>^ gr1;   // C3392
   GR<R^, V, N2^>^ gr1a; // OK

   GR<R^, N^, N^>^ gr3;  // C3392
   GR<R^, V, N2^>^ gr3a; // OK

   GR<R^, V, R^>^ gr4;   // C3392
   GR<R^, V, R2^>^ gr4a; // OK
}
```
