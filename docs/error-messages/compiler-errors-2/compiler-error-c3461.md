---
title: 编译器错误 C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: c5195e0a9bba1bc9e5962f3d3ae1795bb098be3d
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742874"
---
# <a name="compiler-error-c3461"></a>编译器错误 C3461

“type”：仅可转发托管类型

类型转发只会在 CLR 类型上发生。  有关详细信息，请参阅 [类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md) 。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

下面的示例生成 C3461。

```cpp
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```
