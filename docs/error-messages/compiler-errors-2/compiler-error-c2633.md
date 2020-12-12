---
description: 了解更多：编译器错误 C2633
title: 编译器错误 C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: 182cafdd9a79744414a89792e1361c8173077705
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123443"
---
# <a name="compiler-error-c2633"></a>编译器错误 C2633

"identifier"： "inline" 是构造函数的唯一合法存储类

构造函数被声明为非内联的存储类。

下面的示例生成 C2633：

```cpp
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```
