---
description: '了解详细信息： true (c + +) '
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: 6f3a9a183a30057ab3a013dad6e03458e6532658
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186449"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>语法

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>备注

此关键字是 [bool](../cpp/bool-cpp.md) 类型的变量或条件表达式的两个值中的一个， (条件表达式现在为真正的布尔表达式) 。 如果 `i` 的类型为 **`bool`** ，则语句将 `i = true;` 分配 **`true`** 给 `i` 。

## <a name="example"></a>示例

```cpp
// bool_true.cpp
#include <stdio.h>
int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)
