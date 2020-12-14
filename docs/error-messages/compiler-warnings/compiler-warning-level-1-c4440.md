---
description: 了解详细信息：编译器警告 (等级 1) C4440
title: 编译器警告（等级 1）C4440
ms.date: 11/04/2016
f1_keywords:
- C4440
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
ms.openlocfilehash: 9e0a126ea1461e0b98bcef5117b893ea232fe262
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311040"
---
# <a name="compiler-warning-level-1-c4440"></a>编译器警告（等级 1）C4440

忽略从 "calling_convention1" 到 "calling_convention2" 的调用约定重定义

已忽略更改调用约定的尝试。

下面的示例生成 C4440：

```cpp
// C4440.cpp
// compile with: /W1 /LD /clr
typedef void __clrcall F();
typedef F __cdecl *PFV;   // C4440
```
