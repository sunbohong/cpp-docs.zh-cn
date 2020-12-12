---
description: 了解更多：编译器错误 C3217
title: 编译器错误 C3217
ms.date: 11/04/2016
f1_keywords:
- C3217
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
ms.openlocfilehash: 3e38c188f5e6d061312cc9994e86143a6661a287
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173709"
---
# <a name="compiler-error-c3217"></a>编译器错误 C3217

“param”: 泛型参数不能在此声明中进行约束

约束的格式错误；约束泛型参数必须与泛型类模板参数一致。

下面的示例生成 C3217：

```cpp
// C3217.cpp
// compile with: /clr
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T : A   // C3217
   void f();
};
```

以下示例演示了可能的解决方法：

```cpp
// C3217b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T1 : A
   void f();
};
```
