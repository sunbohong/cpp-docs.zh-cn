---
description: 了解更多：编译器错误 C2351
title: 编译器错误 C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: ae8cf10cff4a345ee067519d250210f72e6690f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145478"
---
# <a name="compiler-error-c2351"></a>编译器错误 C2351

过时的 c + + 构造函数初始化语法

在构造函数的新样式初始化列表中，必须显式命名每个直接基类，即使它是唯一的基类。

下面的示例生成 C2351：

```cpp
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```
