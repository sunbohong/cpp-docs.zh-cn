---
description: 了解更多：编译器错误 C2801
title: 编译器错误 C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: ca7e74f99b91b5a6699cdf3361ab64a89b7a7392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297468"
---
# <a name="compiler-error-c2801"></a>编译器错误 C2801

"operator operator" 必须是非静态成员

以下运算符只能重载为非静态成员：

- #A1 `=`

- 类成员访问 `->`

- 下标 `[]`

- 函数调用 `()`

可能的 C2801 原因：

- 重载运算符不是类、结构或联合成员。

- 已声明重载运算符 **`static`** 。

- 下面的示例生成 C2801：

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
