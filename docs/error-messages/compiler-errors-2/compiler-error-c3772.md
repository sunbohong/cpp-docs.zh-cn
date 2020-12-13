---
description: 了解更多：编译器错误 C3772
title: 编译器错误 C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 679c5bc47e9b31ebf085dec63a46549a10484cac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340120"
---
# <a name="compiler-error-c3772"></a>编译器错误 C3772

“name”: 友元模板声明无效

声明类模板专用化的友元无效。 不能声明一个类模板的显式或部分专用化，也不能在同一语句中声明该专用化的友元。 *名称* 占位符标识无效的声明。

### <a name="to-correct-this-error"></a>更正此错误

- 不能声明类模板专用化的友元。

- 如果对应用程序适用，请声明类模板的友元，或声明特定部分专用化或显式专用化的友元。

## <a name="example"></a>示例

下面的代码示例失败，因为它声明的是类模板部分专用化的友元。

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>请参阅

[模板](../../cpp/templates-cpp.md)<br/>
[模板专用化](../../cpp/template-specialization-cpp.md)
