---
title: 编译器错误 C3390
description: Microsoft c + + 编译器错误 C3390，其原因和解决方法。
ms.date: 09/26/2020
f1_keywords:
- C3390
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
ms.openlocfilehash: 467b379d7f5a349a217b566dc55b28d5fbd789da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414355"
---
# <a name="compiler-error-c3390"></a>编译器错误 C3390

> "*type_arg*"：泛型 "*generic_type*" 的泛型参数 "*param*" 的类型参数无效，它必须是引用类型

泛型类型实例化错误。 检查类型定义。

## <a name="remarks"></a>备注

有关详细信息，请参阅[泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="example"></a>示例

第一个示例使用 c # 创建包含泛型类型的组件。 在 c + +/CLI 中创作泛型类型时，此类型具有某些不受支持的约束 有关详细信息，请参阅[类型参数的约束](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters)。

```csharp
// C3390.cs
// Compile by using: csc /target:library C3390.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

当 C3390.dll 组件可用时，以下示例生成 C3390。

```cpp
// C3390_b.cpp
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>
ref class R { R(int) {} };
value class V {};
ref struct N { N() {} };

int main () {
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type
   GR<R^, V, N^>^ gr2b; // OK - do this instead
}
```
