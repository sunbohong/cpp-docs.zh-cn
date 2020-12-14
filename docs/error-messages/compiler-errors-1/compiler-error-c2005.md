---
description: 了解更多：编译器错误 C2005
title: 编译器错误 C2005
ms.date: 11/04/2016
f1_keywords:
- C2005
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
ms.openlocfilehash: 80ed80433d2e227b4c904d6ce4a68318feb98b05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298573"
---
# <a name="compiler-error-c2005"></a>编译器错误 C2005

\#行应为行号，却找到 "token"

`#line`指令后面必须跟有行号。

下面的示例生成 C2005：

```cpp
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

可能的解决方法：

```cpp
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```
