---
description: 了解更多：编译器错误 C2133
title: 编译器错误 C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: d98cb3bd8df5543ecf0426a146157300f67dd91b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323124"
---
# <a name="compiler-error-c2133"></a>编译器错误 C2133

"identifier"：未知的大小

成员列表数组数组被声明为类、结构、联合或枚举的成员。 /Za (ANSI C) 选项不允许成员列表数组成员数组。

下面的示例生成 C2133：

```cpp
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

可能的解决方法：

```cpp
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```
