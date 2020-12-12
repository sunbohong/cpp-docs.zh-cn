---
description: 详细了解：编译器警告 (等级 3) C4522
title: 编译器警告（等级 3）C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: 8663bf6ea70edd6612fd3d124989f6e657185947
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257961"
---
# <a name="compiler-warning-level-3-c4522"></a>编译器警告（等级 3）C4522

"class"：指定了多个赋值运算符

类具有单个类型的多个赋值运算符。 此警告是信息性的;构造函数可在程序中调用。

使用 [警告](../../preprocessor/warning.md) 杂注来禁止显示此警告。

## <a name="example"></a>示例

下面的示例生成 C4522。

```cpp
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```
