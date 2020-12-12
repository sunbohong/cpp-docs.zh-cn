---
description: 了解更多：编译器错误 C2512
title: 编译器错误 C2512
ms.date: 02/09/2018
f1_keywords:
- C2512
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
ms.openlocfilehash: 40574ab7fc54ba678729429401ed14fefefe9ebd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212904"
---
# <a name="compiler-error-c2512"></a>编译器错误 C2512

> "*identifier*"：没有合适的默认构造函数可用

*默认构造* 函数（不需要参数的构造函数）不可用于指定的类、结构或联合。 仅当未提供用户定义的构造函数时，编译器才提供默认构造函数。

如果您提供了一个采用非 void 参数的构造函数，并且您希望允许在不使用任何参数的情况下创建类 (例如，作为数组的元素) 时，还必须提供默认构造函数。 默认构造函数可以是一个所有参数都使用默认值的构造函数。

## <a name="example"></a>示例

错误 C2512 的一个常见原因是，定义了采用参数的类或结构构造函数，然后尝试在不使用任何参数的情况下声明类或结构的实例。 例如， `struct B` 下面声明了一个需要参数的构造函数 `char *` ，但不使用不带任何参数的构造函数。 在中 `main` ，声明了 B 的实例，但未提供任何参数。 编译器会生成 C2512，因为它找不到 B 的默认构造函数。

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

可以通过为结构或类定义默认构造函数（如 `B() {}` ）或构造函数（其中所有参数都具有默认值，例如），来解决此问题 `B (char * = nullptr) {}` 。
