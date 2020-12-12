---
description: 了解更多：编译器错误 C2929
title: 编译器错误 C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: b110615a05a416b6bba7256c7f59f734179677a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320382"
---
# <a name="compiler-error-c2929"></a>编译器错误 C2929

“identifier”：显式实例化；无法显式强制和取消模板类成员的实例化

不能在防止标识符实例化的同时对其进行显式实例化。

下面的示例生成 C2929：

```cpp
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```
