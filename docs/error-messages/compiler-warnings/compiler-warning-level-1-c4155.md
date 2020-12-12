---
description: 了解详细信息：编译器警告 (等级 1) C4155
title: 编译器警告（等级 1）C4155
ms.date: 11/04/2016
f1_keywords:
- C4155
helpviewer_keywords:
- C4155
ms.assetid: ba233353-09e3-4195-8127-13a27ddd8d70
ms.openlocfilehash: 04ea5ae01799fcda17c3591cf4dbc14daf4236ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267295"
---
# <a name="compiler-warning-level-1-c4155"></a>编译器警告（等级 1）C4155

未使用数组形式的“delete”删除数组表达式

的数组形式 **`delete`** 应该用于删除数组。 此警告只会在 ANSI 兼容性 (/Za) 情况下出现。

## <a name="example"></a>示例

下面的示例生成 C4155：

```cpp
// C4155.cpp
// compile with: /Za /W1
#include <stdio.h>

int main(void)
{
    int (*array)[ 10 ] = new int[ 5 ] [ 10 ];
    array[0][0] = 8;

    printf_s("%d\n", array[0][0]);

   delete array;   // C4155
    // try the following line instead
    // delete [] array;   // C4155
}
```
