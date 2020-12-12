---
description: 了解更多：编译器错误 C3395
title: 编译器错误 C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: 65db71a9dbc076b21d16f3f0c250c20a9b283daa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321964"
---
# <a name="compiler-error-c3395"></a>编译器错误 C3395

"function"：不能将 __declspec (dllexport) 应用于具有 \_ _clrcall 调用约定的函数

`__declspec(dllexport)` 和 [__clrcall](../../cpp/clrcall.md) 不兼容。  有关详细信息，请参阅 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)。

下面的示例生成 C3395：

```cpp
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```
