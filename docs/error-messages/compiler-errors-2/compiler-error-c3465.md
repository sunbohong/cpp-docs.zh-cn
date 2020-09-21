---
title: 编译器错误 C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: 56eeac18d5b8efc32501bf54e2de3aa216e05a13
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742016"
---
# <a name="compiler-error-c3465"></a>编译器错误 C3465

若要使用类型“type”，必须引用程序集“assembly”

在重新编译客户端之前，类型转发都将适用于客户端应用程序。 重新编译时，包含客户端应用程序中所用类型定义的每个程序集都将需要一个引用。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

以下示例生成包含类型新位置的程序集。

```cpp
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

以下示例生成用来包含类型定义的程序集，但现在却包含此类型的转发语法。

```cpp
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

下面的示例生成 C3465。

```cpp
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```
