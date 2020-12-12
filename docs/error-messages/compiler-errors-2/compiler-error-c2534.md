---
description: 了解更多：编译器错误 C2534
title: 编译器错误 C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: fbdc4c292a8eb59ee9ab51de0100455139473f7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302070"
---
# <a name="compiler-error-c2534"></a>编译器错误 C2534

"identifier"：构造函数无法返回值

构造函数不能返回值，也不能具有返回类型 (甚至不能 **`void`**) 返回类型。

通过 **`return`** 从构造函数定义中删除语句，可以解决此错误。

下面的示例生成 C2534：

```cpp
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```
