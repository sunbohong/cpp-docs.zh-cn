---
title: 编译器错误 C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: dd7046fcf87a6b8f095092ef0de4b94326151e87
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742822"
---
# <a name="compiler-error-c3467"></a>编译器错误 C3467

“type”：此类型已被转发

编译器找到了同一类型的多个转发类型声明。 每个类型只允许具有一个声明。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

下面的示例生成 C3467。

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
