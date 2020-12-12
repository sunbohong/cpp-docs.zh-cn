---
description: 了解更多：编译器错误 C2092
title: 编译器错误 C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: 3f89d735d44b3cc0b2c28013ab957bf433159afb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251877"
---
# <a name="compiler-error-c2092"></a>编译器错误 C2092

"array name" 数组元素类型不能为函数

不允许使用函数的数组。 使用指向函数的指针的数组。

## <a name="examples"></a>示例

下面的示例生成 C2092：

```cpp
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

可能的解决方法：

```cpp
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```
