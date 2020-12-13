---
description: 了解更多：编译器错误 C2273
title: 编译器错误 C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: 656b5477682ace779cd872b2233d911cfb67c0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336264"
---
# <a name="compiler-error-c2273"></a>编译器错误 C2273

"type"： "->" 运算符右侧的非法

类型显示为运算符的右操作数 `->` 。

尝试访问用户定义的类型转换可能会导致此错误。 使用关键字 **`operator`** -> 和 `type` 。

下面的示例生成 C2273：

```cpp
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```
