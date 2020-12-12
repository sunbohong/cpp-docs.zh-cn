---
description: 了解更多：编译器错误 C3886
title: 编译器错误 C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: ed82fcc8a21d19f88bf9381431711e3a7a397c6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144347"
---
# <a name="compiler-error-c3886"></a>编译器错误 C3886

"var"：必须初始化 literal 数据成员

在 declaraed [文本](../../extensions/literal-cpp-component-extensions.md) 变量时，必须对其进行初始化。

下面的示例生成 C3886：

```cpp
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```
