---
description: 了解更多：编译器错误 C3227
title: 编译器错误 C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: 26d66bf3e0c3bc3a6f391d66608f3e6790b2d11d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304137"
---
# <a name="compiler-error-c3227"></a>编译器错误 C3227

"parameter"：不能使用 "关键字" 来分配泛型类型

为了实例化类型，需要一个适当的构造函数。 但编译器无法确保适当的构造函数可用。

您可以使用模板（而不是泛型）来解决此错误，也可以使用多种方法之一来创建该类型的实例。

## <a name="example"></a>示例

下面的示例生成 C3227。

```cpp
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```
