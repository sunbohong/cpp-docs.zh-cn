---
title: 编译器错误 C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: ed645535300e0a7c4d27f8bed43d3143bae7e97a
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742861"
---
# <a name="compiler-error-c3225"></a>编译器错误 C3225

"arg" 的泛型类型参数不能是 "type"，它必须是值类型或句柄类型

泛型类型参数的类型不正确。

有关详细信息，请参阅[泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="examples"></a>示例

不能使用本机类型来实例化泛型类型。 下面的示例生成 C3225。

```cpp
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

下面的示例使用 c # 创建组件。 请注意，约束指定只能使用值类型实例化泛型类型。

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

此示例使用 c # 编写的组件，并违反了 MyList 只能使用以外的值类型进行实例化的约束 <xref:System.Nullable> 。 下面的示例生成 C3225。

```cpp
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```
