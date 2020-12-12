---
description: 了解更多：编译器错误 C2957
title: 编译器错误 C2957
ms.date: 11/04/2016
f1_keywords:
- C2957
helpviewer_keywords:
- C2957
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
ms.openlocfilehash: 7d5539f43651feb930b3eb0f81677aaed0fa6b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210577"
---
# <a name="compiler-error-c2957"></a>编译器错误 C2957

“delim”: 无效的左侧分隔符: 应为“<”

泛型类格式不正确。

下面的示例生成 C2957：

```cpp
// C2957.cpp
// compile with: /clr /LD
generic << class T>   // C2957
// try the following line instead
// generic < class T>
gc class C {};
```
