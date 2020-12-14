---
description: 了解更多：编译器错误 C2014
title: 编译器错误 C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 2f8de1d2b9ea8ef680826cfbfc189dbe2617c9f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220976"
---
# <a name="compiler-error-c2014"></a>编译器错误 C2014

预处理器命令必须作为第一个非空白空间启动

`#`预处理器指令的符号必须是不是空格的行上的第一个字符。

下面的示例生成 C2014：

```cpp
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

可能的解决方法：

```cpp
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```
