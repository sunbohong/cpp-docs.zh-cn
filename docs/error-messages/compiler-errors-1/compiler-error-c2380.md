---
description: 了解更多：编译器错误 C2380
title: 编译器错误 C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: 4455fef072b6d8f686d5f43130db8d02aba69fd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174684"
---
# <a name="compiler-error-c2380"></a>编译器错误 C2380

键入 (s) 前面的 "identifier" (构造函数（具有返回类型）或当前类名称的非法重定义？ ) 

构造函数返回值或重新定义类名称。

下面的示例生成 C2326:

```cpp
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```
