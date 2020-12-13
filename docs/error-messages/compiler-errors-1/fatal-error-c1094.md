---
description: 了解详细信息：严重错误 C1094
title: 错误 C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: af83c6fa80a6e1b115146ad05513539fea7d348c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145088"
---
# <a name="fatal-error-c1094"></a>错误 C1094

"-Zmval1"：命令行选项与用于生成预编译标头 ( "-Zmval2" 的值不一致 ) 

传递给 [/yc](../../build/reference/yc-create-precompiled-header-file.md) 的值必须与传递给 [/yu](../../build/reference/yu-use-precompiled-header-file.md) (**/zm** 值的值在使用或创建相同预编译头文件) 的所有编译中必须相同。

下面的示例生成 C1094：

```
// C1094.h
int func1();
```

然后，

```cpp
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

然后，

```cpp
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```
