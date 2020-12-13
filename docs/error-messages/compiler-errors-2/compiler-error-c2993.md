---
description: 了解更多：编译器错误 C2993
title: 编译器错误 C2993
ms.date: 11/04/2016
f1_keywords:
- C2993
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
ms.openlocfilehash: 2c43d4f3e54378d419f1945b1f6b38e9ee4d9758
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136417"
---
# <a name="compiler-error-c2993"></a>编译器错误 C2993

"identifier"：非类型模板参数 "parameter" 的类型非法

不能声明具有结构或联合参数的模板。 使用指针将结构和联合作为模板参数传递。

下面的示例生成 C2993：

```cpp
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

在 Visual Studio .NET 2003：不再允许使用浮点非类型模板参数的情况下，也会生成此错误。 C + + 标准不允许浮点非类型模板参数。

如果它是函数模板，请使用函数参数传入浮点非类型模板参数 (此代码在 Visual Studio .NET 2003 和 Visual Studio .NET 版本的 Visual C++) 中是有效的。 如果它是类模板，则没有简单的解决方法。

```cpp
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```
