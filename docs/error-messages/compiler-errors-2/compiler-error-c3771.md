---
description: 了解更多：编译器错误 C3771
title: 编译器错误 C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: f7d71952411632ded02bc5121c6f6668eddeabc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291657"
---
# <a name="compiler-error-c3771"></a>编译器错误 C3771

“标识符”: 在最近的命名空间范围内无法找到友元声明

无法在当前命名空间中找到指定模板的类模板声明 *标识符* 。

### <a name="to-correct-this-error"></a>更正此错误

- 确保在当前命名空间中定义了模板标识符的类模板声明，或模板标识符是完全限定的名称。

## <a name="example"></a>示例

下列代码示例在 `NA`命名空间中声明一个类模板和函数，但试图在 `NB`命名空间中声明友元函数模板。

```cpp
// C3771.cpp
// compile with: /c

namespace NA {
template<class T> class A {
    void aFunction(T t) {};
    };
}
// using namespace NA;
namespace NB {
    class X {
        template<class T> friend void A<T>::aFunction(T); // C3771
// try the following line instead
//      template<class T> friend void NA::A<T>::aFunction(T);
// or try "using namespace NA;" instead.
    };
}
```

## <a name="see-also"></a>请参阅

[模板](../../cpp/templates-cpp.md)
