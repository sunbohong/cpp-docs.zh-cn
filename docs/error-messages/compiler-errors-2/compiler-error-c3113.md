---
description: 了解更多：编译器错误 C3113
title: 编译器错误 C3113
ms.date: 11/04/2016
f1_keywords:
- C3113
helpviewer_keywords:
- C3113
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
ms.openlocfilehash: dcad27e26e0795b8d1901cca51dc5cd16a88ae5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115984"
---
# <a name="compiler-error-c3113"></a>编译器错误 C3113

"结构" 不能是模板/泛型

您尝试将类模板或类泛型从接口或枚举中排除。

下面的示例生成 C3113：

```cpp
// C3113.cpp
// compile with: /c
template <class T>
enum E {};   // C3113
// try the following line instead
// class MyClass{};
```
