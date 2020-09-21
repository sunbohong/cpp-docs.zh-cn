---
title: 编译器错误 C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: f22a01c5c26a55a5908c20f3b123971fadd43544
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742809"
---
# <a name="compiler-error-c3468"></a>编译器错误 C3468

“type”: 只能将类型转发到程序集:

“`file`”不是程序集

只能转发程序集中的类型。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个模块。

```cpp
// C3468.cpp
// compile with: /LN /clr
public ref class R {};
```

下面的示例生成 C3468。

```cpp
// C3468_b.cpp
// compile with: /clr /c
#using "C3468.netmodule"
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468
```
