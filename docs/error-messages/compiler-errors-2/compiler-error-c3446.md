---
description: 了解更多：编译器错误 C3446
title: 编译器错误 C3446
ms.date: 07/21/2017
f1_keywords:
- C3446
helpviewer_keywords:
- C3446
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
ms.openlocfilehash: 442ac07c1684278e76f86531d1c28de6507eb999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113654"
---
# <a name="compiler-error-c3446"></a>编译器错误 C3446

>"*class*"：值类的成员不允许使用默认成员初始值设定项

在 Visual Studio 2015 及更早版本中，编译器允许（但会忽略）值类成员的默认成员初始值设定项。 值类的默认初始化始终对成员执行零初始化；不允许使用默认构造函数。 在 Visual Studio 2017 中，默认成员初始值设定项引发编译器错误，如下例所示：

## <a name="example"></a>示例

下面的示例在 Visual Studio 2017 和更高版本中生成 C3446：

```cpp
// C3446.cpp
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer
                  // is not allowed for a member of a value class
       int j {0}; // C3446
};
```

若要更正此错误，请删除初始值设定项：

```cpp
// C3446b.cpp
value struct V
{
       int i;
       int j;
};
```
