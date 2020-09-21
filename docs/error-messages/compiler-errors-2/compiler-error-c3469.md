---
title: 编译器错误 C3469
ms.date: 11/04/2016
f1_keywords:
- C3469
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
ms.openlocfilehash: 32d61e022de47b95ce3e84f1575cc090c74d70e3
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742796"
---
# <a name="compiler-error-c3469"></a>编译器错误 C3469

“type”：不能转发泛型类

不能对泛型类使用类型转发。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C3469.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

下面的示例生成 C3466。

```cpp
// C3469_b.cpp
// compile with: /clr /c
#using "C3469.dll"
[assembly:TypeForwardedTo(GR::typeid)];   // C3469
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
