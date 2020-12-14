---
description: 了解更多：编译器错误 C2768
title: 编译器错误 C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 0911153b9b89996631433d8a19bde9d19fc5f6b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239462"
---
# <a name="compiler-error-c2768"></a>编译器错误 C2768

"function"：非法使用显式模板参数

编译器无法确定函数定义是否应该是函数模板的显式专用化，或函数定义是否应为新函数。

此错误是在 Visual Studio .NET 2003 中引入的，作为编译器一致性增强的一部分。

下面的示例生成 C2768：

```cpp
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```
