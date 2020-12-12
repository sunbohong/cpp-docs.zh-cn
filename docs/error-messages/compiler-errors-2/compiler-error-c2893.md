---
description: 了解更多：编译器错误 C2893
title: 编译器错误 C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: 42e31327096a539feeb691c698b52f57ecb615a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278254"
---
# <a name="compiler-error-c2893"></a>编译器错误 C2893

未能使函数模板 "template name" 专用化

编译器未能使函数模板专用化。 此问题的原因可能有很多。

通常，解决 C2893 错误的方法是查看函数的签名，并确保可以实例化每个类型。

## <a name="example"></a>示例

发生 C2893 的原因是 `f` ，的模板参数 `T` 被推导为 `std::map<int,int>` ，但没有 `std::map<int,int>` 成员 `data_type` (`T::data_type` 不能 ) 实例化 `T = std::map<int,int>` 。 下面的示例生成 C2893。

```cpp
// C2893.cpp
// compile with: /c /EHsc
#include<map>
using namespace std;
class MyClass {};

template<class T>
inline typename T::data_type
// try the following line instead
// inline typename  T::mapped_type
f(T const& p1, MyClass const& p2);

template<class T>
void bar(T const& p1) {
    MyClass r;
    f(p1,r);   // C2893
}

int main() {
   map<int,int> m;
   bar(m);
}
```
