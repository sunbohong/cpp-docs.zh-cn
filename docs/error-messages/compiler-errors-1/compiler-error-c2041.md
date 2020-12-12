---
description: 了解更多：编译器错误 C2041
title: 编译器错误 C2041
ms.date: 11/04/2016
f1_keywords:
- C2041
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
ms.openlocfilehash: 5c980b6783b4b14e4878278699e5b4f7618ff0f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175256"
---
# <a name="compiler-error-c2041"></a>编译器错误 C2041

基 "number" 的非法数字 "character"

指定的字符不是基本 (的有效数字，如八进制或十六进制) 。

下面的示例生成 C2041：

```cpp
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

可能的解决方法：

```cpp
// C2041b.cpp
// compile with: /c
int j = 071;
```
