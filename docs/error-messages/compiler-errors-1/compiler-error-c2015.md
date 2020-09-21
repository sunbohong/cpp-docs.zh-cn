---
title: 编译器错误 C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 5453009e1c2bd091ed3507f3c43bd7fcecd33abc
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743095"
---
# <a name="compiler-error-c2015"></a>编译器错误 C2015

常量中的字符太多

字符常量包含两个以上的字符。 对于标准字符常量，长度限制为一个字符，长字符常量限制为两个字符。

转义序列（如 \t）转换为单个字符。

## <a name="examples"></a>示例

下面的示例生成 C2015：

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

使用 Microsoft 扩展时，也会发生 C2015，转换为整数。  下面的示例生成 C2015：

```cpp
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```
