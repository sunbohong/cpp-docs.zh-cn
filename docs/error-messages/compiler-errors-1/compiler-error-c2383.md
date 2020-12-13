---
description: 了解更多：编译器错误 C2383
title: 编译器错误 C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 862346d7f2bfe92a5d2182a7fe53f260b357ad0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185929"
---
# <a name="compiler-error-c2383"></a>编译器错误 C2383

"*symbol*"：此符号上不允许使用默认参数

C + + 编译器不允许指向函数的指针的默认参数。

Visual Studio 2005 之前的版本中的 Microsoft c + + 编译器接受此代码，但现在提供错误。 对于在所有版本的 Visual C++ 中都有效的代码，请不要为指向函数的指针参数赋值。

## <a name="example"></a>示例

下面的示例生成 C2383，并显示一个可能的解决方案：

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
