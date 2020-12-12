---
description: 了解更多：编译器错误 C2086
title: 编译器错误 C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: b98b4ed3896b11d8df434935c1b539f76640f24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252072"
---
# <a name="compiler-error-c2086"></a>编译器错误 C2086

"identifier"：重定义

多次定义该标识符，或后续声明与前一个声明不同。

C2086 也可以是针对引用的 c # 程序集进行增量生成的结果。 重新生成 c # 程序集以解决此错误。

下面的示例生成 C2086：

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
