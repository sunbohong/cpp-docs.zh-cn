---
description: 了解详细信息：编译器警告 (等级 1) C4615
title: 编译器警告（等级 1）C4615
ms.date: 11/04/2016
f1_keywords:
- C4615
helpviewer_keywords:
- C4615
ms.assetid: 7b107c01-0da2-4e01-8b40-93813e30b94c
ms.openlocfilehash: 174ffa81e9f5927833b877ede7cf24ae530b94fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339214"
---
# <a name="compiler-warning-level-1-c4615"></a>编译器警告（等级 1）C4615

\#pragma warning：未知的用户警告类型

与 **杂注**[警告](../../preprocessor/warning.md)一起使用了无效的警告说明符。 若要解决此错误，请使用有效的警告说明符。

下面的示例生成 C4615：

```cpp
// C4615.cpp
// compile with: /W1 /LD
#pragma warning(enable : 4401)   // C4615, 'enable' not valid specifier

// use the code below to resolve the error
// #pragma warning(default : 4401)
```
