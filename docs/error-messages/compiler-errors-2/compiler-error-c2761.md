---
description: 了解更多：编译器错误 C2761
title: 编译器错误 C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 624a375aedc78b6d63f3a6c5a1185edfade28c7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336148"
---
# <a name="compiler-error-c2761"></a>编译器错误 C2761

"function"：不允许使用成员函数重新声明

不能重新声明成员函数。 你可以定义它，但不能重新声明它。

## <a name="examples"></a>示例

下面的示例生成 C2761。

```cpp
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761
```

不能定义类或结构的非静态成员。  下面的示例生成 C2761。

```cpp
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```
