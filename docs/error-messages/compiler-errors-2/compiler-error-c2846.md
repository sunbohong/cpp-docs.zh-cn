---
description: 了解更多：编译器错误 C2846
title: 编译器错误 C2846
ms.date: 11/04/2016
f1_keywords:
- C2846
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
ms.openlocfilehash: ecd6d480bdd485e3c623da8563c7f0eefe8e70c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260223"
---
# <a name="compiler-error-c2846"></a>编译器错误 C2846

"构造函数"：接口不能有构造函数

Visual C++ [接口](../../cpp/interface.md) 不能有构造函数。

下面的示例生成 C2846：

```cpp
// C2846.cpp
// compile with: /c
__interface C {
   C();   // C2846 constructor not allowed in an interface
};
```
