---
description: 了解更多：编译器错误 C2228
title: 编译器错误 C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 8bf5c4af88f77237699baae5e7a458fca971f126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195055"
---
# <a name="compiler-error-c2228"></a>编译器错误 C2228

“.identifier”的左边必须有类/结构/联合

句点 ( 的左操作数。 ) 不是类、结构或联合。

下面的示例生成 C2228：

```cpp
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

如果在使用托管扩展时用了不正确的语法，也会看到此错误。 而在其他 Visual Studio 语言中，可以使用点运算符访问托管类的成员，指向 C++ 中对象的指针意味着你需要使用 -> 运算符来访问该成员:

错误： `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

正确： `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
