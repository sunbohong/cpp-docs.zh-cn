---
description: 了解更多：编译器错误 C2054
title: 编译器错误 C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: b86c805a5687679cfa4bb5ed667c3bcf3adbad94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341355"
---
# <a name="compiler-error-c2054"></a>编译器错误 C2054

应输入 " (" 跟踪 "identifier"

函数标识符用于需要尾随括号的上下文中。

此错误可能是由于对复杂的初始化省略了等号 (=) 导致的。

下面的示例生成 C2054：

```c
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

可能的解决方法：

```c
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```
