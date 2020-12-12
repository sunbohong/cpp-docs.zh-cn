---
description: 了解更多：编译器错误 C2006
title: 编译器错误 C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 5747f5417db60bd3c1f7bc1420c257552a9b42c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298508"
---
# <a name="compiler-error-c2006"></a>编译器错误 C2006

"指令" 应为文件名，却找到 "token"

指令（如 [#include](../../preprocessor/hash-include-directive-c-cpp.md) 或 [#import](../../preprocessor/hash-import-directive-cpp.md) ）需要文件名。 若要解决此错误，请确保 *token* 是有效的文件名。 同时，将文件名置于双引号或尖括号中。

下面的示例生成 C2006：

```cpp
// C2006.cpp
#include stdio.h   // C2006
```

可能的解决方法：

```cpp
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```
