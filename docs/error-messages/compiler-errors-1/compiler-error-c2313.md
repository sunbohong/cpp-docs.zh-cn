---
description: 了解更多：编译器错误 C2313
title: 编译器错误 C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 455bc3a833f576c051ff1531d921f8504789810e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282144"
---
# <a name="compiler-error-c2313"></a>编译器错误 C2313

“type1”：由引用（“type2”）在行号上捕获

异常类型有两个处理程序。 第二个 catch 的类型是对第一个类型的引用。

以下示例生成 C2313：

```cpp
// C2313.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
    try {
        throw "ooops!";
    }
    catch( C& ) {}
    catch( C ) {}   // C2313
}
```
