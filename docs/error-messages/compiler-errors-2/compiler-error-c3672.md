---
description: 了解更多：编译器错误 C3672
title: 编译器错误 C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: aea8a03e409e1144985cb7b94dcca94975d58db5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228815"
---
# <a name="compiler-error-c3672"></a>编译器错误 C3672

伪析构函数表达式只能用作函数调用的一部分

错误地调用了析构函数。  有关详细信息，请参阅 [析构函数](../../cpp/destructors-cpp.md)。

## <a name="example"></a>示例

下面的示例生成 C3672。

```cpp
// C3672.cpp
template<typename T>
void f(T* pT) {
   &pT->T::~T;   // C3672
   pT->T::~T();   // OK
};

int main() {
   int i;
   f(&i);
}
```
