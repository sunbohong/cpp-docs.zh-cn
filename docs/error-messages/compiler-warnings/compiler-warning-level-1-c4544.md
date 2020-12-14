---
description: 了解详细信息：编译器警告 (等级 1) C4544
title: 编译器警告（等级 1）C4544
ms.date: 11/04/2016
f1_keywords:
- C4544
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
ms.openlocfilehash: cd7d4dddd43a8cac0ce4eb5115dbbadad3d56103
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294751"
---
# <a name="compiler-warning-level-1-c4544"></a>编译器警告（等级 1）C4544

“declaration”：已忽略此模板声明中的默认模板自变量

默认模板自变量在错误的位置指定，并且已被忽略。 类模板的默认模板参数只能在类模板的声明或定义中指定，不能在类模板的成员上指定。

此示例生成 C4545，而下一个示例演示如何修复此问题：

```cpp
// C4544.cpp
// compile with: /W1 /LD
template <class T>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T=int>
template <class T1>
struct S<T>::S1 {};   // C4544
```

在此示例中，默认参数应用于类模板 `S`：

```cpp
// C4544b.cpp
// compile with: /LD
template <class T = int>
struct S
{
   template <class T1>
      struct S1;
   void f();
};

template <class T>
template <class T1>
struct S<T>::S1 {};
```
