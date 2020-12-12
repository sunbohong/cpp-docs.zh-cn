---
description: 了解更多：编译器错误 C2252
title: 编译器错误 C2252
ms.date: 11/04/2016
f1_keywords:
- C2252
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
ms.openlocfilehash: 491ec4c600ab480322917d50822ede01a08dcfb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134818"
---
# <a name="compiler-error-c2252"></a>编译器错误 C2252

无法在当前范围内显式实例化模板

编译器检测到模板的显式实例化有问题。  例如，不能在函数中显式实例化模板。

下面的示例生成 C2252：

```cpp
// C2252.cpp
class A {
public:
   template <class T>
   int getit(int i , T * it ) {
      return i;
   }
   template int A::getit<double>(int i, double * it);   // C2252
   // try the following line instead
   // template <> int A::getit<double>(int i, double * it);

};

int main() {
   // cannot explicitly instantiate in function
   template int A::getit<long>(int i, long * it);   // C2252
}
```
