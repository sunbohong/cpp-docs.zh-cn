---
description: 了解更多：编译器错误 C2675
title: 编译器错误 C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: 71d52a8da09861078811757ad7af7c757e418e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282024"
---
# <a name="compiler-error-c2675"></a>编译器错误 C2675

一元 "operator"： "type" 不定义此运算符或对预定义运算符可接受的类型的转换

使用一元运算符时，该类型不会定义运算符，也不会将转换为预定义运算符可接受的类型。 要使用该运算符，必须针对指定类型将其重载，或者定义一个到某个类型（该运算符已针对此类型进行了定义）的转换。

## <a name="example"></a>示例

下面的示例生成 C2675。

```cpp
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```
