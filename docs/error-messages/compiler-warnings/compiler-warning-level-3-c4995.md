---
description: 详细了解：编译器警告 (等级 3) C4995
title: 编译器警告 (等级 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: bb63802edf523fb0816bc6aeec289839b99b1110
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332052"
---
# <a name="compiler-warning-level-3-c4995"></a>编译器警告 (等级 3) C4995

"function"：名称被标记为 #pragma 不推荐使用

编译器遇到了已 [使用杂注](../../preprocessor/deprecated-c-cpp.md)标记的函数。 在未来版本中可能不再支持此函数。 可以关闭此警告，并在下面的 [警告](../../preprocessor/warning.md) 杂注 (示例) 。

## <a name="example"></a>示例

下面的示例生成 C4995：

```cpp
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```
