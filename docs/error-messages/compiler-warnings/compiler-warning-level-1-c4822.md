---
description: 了解详细信息：编译器警告 (等级 1) C4822
title: 编译器警告（等级 1）C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 8e5fe62d70243da0121d58e553c500e5a079022a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198045"
---
# <a name="compiler-warning-level-1-c4822"></a>编译器警告（等级 1）C4822

“member”：局部类成员函数没有函数体

在类中声明了某个局部类成员函数，但并未定义。 若要使用局部类成员函数，必须在类中定义。 不能在类中声明而在类外定义。

在类外定义局部类成员函数将出现错误。

以下示例生成 C4822：

```cpp
// C4822.cpp
// compile with: /W1
int main() {
   struct C {
      void func1(int);   // C4822
      // try the following line instead
      // void func1(int){}
  };
}
```
