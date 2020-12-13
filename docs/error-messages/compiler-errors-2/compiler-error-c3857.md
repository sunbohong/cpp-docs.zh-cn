---
description: 了解更多：编译器错误 C3857
title: 编译器错误 C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 6d4dacfc8bf18f7f2b9665058bbd418eb0615912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336139"
---
# <a name="compiler-error-c3857"></a>编译器错误 C3857

"type"：不允许使用多个类型参数列表

为同一个类型指定了多个模板或泛型，这是不允许的。

下面的示例生成 C3857：

```cpp
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

可能的解决方法：

```cpp
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

使用泛型时也可能发生 C3857：

```cpp
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

可能的解决方法：

```cpp
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```
