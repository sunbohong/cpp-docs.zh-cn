---
description: 了解更多：编译器错误 C2503
title: 编译器错误 C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: 941af8af7fc4399e3c091b9d12a882619f4fc62c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213086"
---
# <a name="compiler-error-c2503"></a>编译器错误 C2503

"class"：基类不能包含零大小的数组

基类或结构包含大小为零的数组。 类中的数组必须具有至少一个元素。

下面的示例生成 C2503：

```cpp
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```
