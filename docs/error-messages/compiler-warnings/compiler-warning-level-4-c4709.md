---
description: 详细了解：编译器警告 (级别 4) C4709
title: 编译器警告（等级 4）C4709
ms.date: 11/04/2016
f1_keywords:
- C4709
helpviewer_keywords:
- C4709
ms.assetid: 8abfdd45-8c70-4c27-b0fb-ca0c3f0fccf9
ms.openlocfilehash: 3138b8d95fd05cac113166ee9de9e7979f08223d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136222"
---
# <a name="compiler-warning-level-4-c4709"></a>编译器警告（等级 4）C4709

数组索引表达式中的逗号运算符

当数组索引表达式中出现逗号时，编译器将使用最后一个逗号后面的值。

## <a name="example"></a>示例

下面的示例生成 C4709：

```cpp
// C4709.cpp
// compile with: /W4
#include <stdio.h>

int main()
{
    int arr[2][2];
    arr[0][0] = 10;
    arr[0][1] = 11;

    // Prints 10, not 11
    printf_s("\n%d",arr[0][1,0]);   // C4709
}
```
