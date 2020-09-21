---
title: 编译器错误 C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 6918e3be0a0288bab50d63a188bc33df87fe7754
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742887"
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
