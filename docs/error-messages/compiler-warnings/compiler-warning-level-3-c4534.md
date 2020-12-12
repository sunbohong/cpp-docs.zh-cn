---
description: 详细了解：编译器警告 (等级 3) C4534
title: 编译器警告（等级 3）C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 6a13b27716488fa04f6342da76fdcd32c5635f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257883"
---
# <a name="compiler-warning-level-3-c4534"></a>编译器警告（等级 3）C4534

由于默认参数，"构造函数" 将不是类 "class" 的默认构造函数

非托管类可以有一个具有默认值的参数的构造函数，并且编译器将使用此构造函数作为默认构造函数。 用关键字标记的类 `value` 不会将具有默认值的构造函数用作默认构造函数。

有关更多信息，请参阅[类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md)。

下面的示例生成 C4534：

```cpp
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```
