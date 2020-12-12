---
description: 了解更多：编译器错误 C3467
title: 编译器错误 C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: c00c78852380537d744c8d01681a921e487826df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113436"
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
