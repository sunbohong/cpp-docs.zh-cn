---
description: 了解更多：函数模板的显式专用化
title: 函数模板的显式专用化
ms.date: 11/04/2016
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
ms.openlocfilehash: c77ebce3383ba2051ac010c39a7dd0eb37b8111a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181496"
---
# <a name="explicit-specialization-of-function-templates"></a>函数模板的显式专用化

利用函数模板，您可以通过为特定类型提供函数模板的显式专用化（重写）来定义该类型的特殊行为。 例如：

```cpp
template<> void MySwap(double a, double b);
```

利用此声明，您可以为变量定义不同的函数 **`double`** 。 与非模板函数一样，标准类型转换 (例如，将类型为的变量升级 **`float`** 为 **`double`**) 。

## <a name="example"></a>示例

```cpp
// explicit_specialization.cpp
template<class T> void f(T t)
{
};

// Explicit specialization of f with 'char' with the
// template argument explicitly specified:
//
template<> void f<char>(char c)
{
}

// Explicit specialization of f with 'double' with the
// template argument deduced:
//
template<> void f(double d)
{
}
int main()
{
}
```

## <a name="see-also"></a>请参阅

[函数模板](../cpp/function-templates.md)
