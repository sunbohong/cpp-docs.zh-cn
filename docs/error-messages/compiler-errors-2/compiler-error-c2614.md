---
description: 了解更多：编译器错误 C2614
title: 编译器错误 C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 5bc0958b406c11299aee9b0d88c4b7b7401370ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338655"
---
# <a name="compiler-error-c2614"></a>编译器错误 C2614

"class1"：非法的成员初始化： "class2" 不是基或成员

只有成员或基类才能出现在类或结构的初始化列表中。

## <a name="example"></a>示例

下面的示例生成 C2614。

```cpp
// C2614.cpp
// compile with: /c
struct A {
   int i;
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A
};

struct A2 {
   int B;
   int i;
   A2( int ia ) : B( i ) {};   // OK
};
```
