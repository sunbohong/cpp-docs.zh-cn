---
description: 了解更多：编译器错误 C3412
title: 编译器错误 C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: aa0dc6cfeac193afc99d003cd821663bcfc139c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313185"
---
# <a name="compiler-error-c3412"></a>编译器错误 C3412

"template"：无法在当前范围内专用化模板

模板不能在类范围内专用化，只能在全局或命名空间范围内使用。

## <a name="examples"></a>示例

下面的示例生成 C3412。

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

下面的示例演示了可能的解决方法。

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
