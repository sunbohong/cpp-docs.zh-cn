---
description: 了解更多：编译器错误 C2951
title: 编译器错误 C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: 7f3030764cdd36d40fbd78a8c3768c7dc1085c21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322102"
---
# <a name="compiler-error-c2951"></a>编译器错误 C2951

类型声明只能在全局、命名空间或类范围内使用

不能将泛型或模板类声明到全局或命名空间范围之外。 如果在包含文件中进行泛型或模板声明，请确保包含文件位于全局范围。

下面的示例生成 C2951：

```cpp
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

使用泛型时也可能发生 C2951：

```cpp
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```
