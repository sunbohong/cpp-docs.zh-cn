---
description: 了解更多：编译器错误 C2012
title: 编译器错误 C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 82f2a5660ec3920c9ff3db57c6ed0b70516c4531
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221002"
---
# <a name="compiler-error-c2012"></a>编译器错误 C2012

"<" 后缺少名称

`#include` 指令缺少必需的文件名。

以下示例生成 C2012：

```cpp
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

可能的解决方法：

```cpp
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```
