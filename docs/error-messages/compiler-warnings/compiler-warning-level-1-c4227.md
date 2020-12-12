---
description: 了解详细信息：编译器警告 (等级 1) C4227
title: 编译器警告（等级 1）C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: f919f3765836548b7aa7410002facd942b942395
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266320"
---
# <a name="compiler-warning-level-1-c4227"></a>编译器警告（等级 1）C4227

使用了记时错误：忽略引用上的限定符

使用 **`const`** 或 **`volatile`** c + + 引用等限定符是一种过时的做法。

## <a name="example"></a>示例

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```
