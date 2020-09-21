---
title: 编译器错误 C2009
ms.date: 11/04/2016
f1_keywords:
- C2009
helpviewer_keywords:
- C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
ms.openlocfilehash: 02780a88552231472c2e16299a6d5e5dfef1bdd2
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743108"
---
# <a name="compiler-error-c2009"></a>编译器错误 C2009

宏形式 “identifier” 重复使用

宏定义的形参列表多次使用标识符。 宏参数列表中的标识符必须是唯一的。

## <a name="examples"></a>示例

下面的示例生成 C2009：

```cpp
// C2009.cpp
#include <stdio.h>

#define macro1(a,a) (a*a)   // C2009

int main()
{
    printf_s("%d\n", macro1(2));
}
```

可能的解决方法：

```cpp
// C2009b.cpp
#include <stdio.h>

#define macro2(a)   (a*a)
#define macro3(a,b) (a*b)

int main()
{
    printf_s("%d\n", macro2(2));
    printf_s("%d\n", macro3(2,4));
}
```
