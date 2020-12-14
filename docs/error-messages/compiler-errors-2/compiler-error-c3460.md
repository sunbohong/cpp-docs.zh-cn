---
description: 了解更多：编译器错误 C3460
title: 编译器错误 C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: ee5bcb2396586d965f16d80ef006301c7bcd784f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315876"
---
# <a name="compiler-error-c3460"></a>编译器错误 C3460

“type”: 仅可转发用户定义的类型

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C3460.cpp
// compile with: /LD /clr
public ref class R {};
```

下面的示例生成 C3460。

```cpp
// C3460_b.cpp
// compile with: /clr /c
#using "C3460.dll"
[assembly:TypeForwardedTo(int::typeid)];   // C3460
[assembly:TypeForwardedTo(R::typeid)];
```
