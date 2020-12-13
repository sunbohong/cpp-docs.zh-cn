---
description: 了解更多：编译器错误 C2249
title: 编译器错误 C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: a9def388d1c9876c8bace8358a08108fdf41394b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337613"
---
# <a name="compiler-error-c2249"></a>编译器错误 C2249

"member"：不能访问在虚拟基 "class" 中声明的成员的路径

`member`继承自非公共 **`virtual`** 基类或结构。

## <a name="examples"></a>示例

下面的示例生成 C2249。

```cpp
// C2249.cpp
class A {
private:
   void privFunc( void ) {};
public:
   void pubFunc( void ) {};
};

class B : virtual public A {} b;

int main() {
   b.privFunc();    // C2249, private member of A
   b.pubFunc();    // OK
}
```

如果尝试将一个流从 c + + 标准库分配到另一个流，也会发生 C2249。  下面的示例生成 C2249。

```cpp
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```
