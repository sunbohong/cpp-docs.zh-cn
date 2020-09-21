---
title: 编译器错误 C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: c4f099ba241b56291074202e6c03ad98ee97f756
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743498"
---
# <a name="compiler-error-c2004"></a>编译器错误 C2004

应输入“defined(id)”

标识符必须出现在括号中，且后接预处理器关键字。

此错误还可能来自于为 Visual Studio .NET 2003 执行的编译器一致性工作：在预处理器指令中缺少括号。 如果预处理器指令中缺少右括号，编译器将生成错误。

## <a name="examples"></a>示例

以下示例生成 C2004：

```cpp
// C2004.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG   // C2004
        printf_s("DEBUG defined\n");
    #endif
}
```

可能的解决方法：

```cpp
// C2004b.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG)
        printf_s("DEBUG defined\n");
    #endif
}
```
