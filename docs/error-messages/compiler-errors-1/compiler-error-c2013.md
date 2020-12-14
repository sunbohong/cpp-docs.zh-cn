---
description: 了解更多：编译器错误 C2013
title: 编译器错误 C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: 2f883c24be5e02c58553ca6f7abe4f588ae8a2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220963"
---
# <a name="compiler-error-c2013"></a>编译器错误 C2013

缺少“>”

`#include` 指令缺少右尖括号。 添加右括号可解决该错误。

下面的示例生成 C2013：

```cpp
// C2013.cpp
#include <stdio.h    // C2013
```

可能的解决方法：

```cpp
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```
