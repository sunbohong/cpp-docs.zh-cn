---
description: 了解更多：编译器错误 C2047
title: 编译器错误 C2047
ms.date: 11/04/2016
f1_keywords:
- C2047
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
ms.openlocfilehash: 40df340017b134a3d2abe092478658f92142298d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175113"
---
# <a name="compiler-error-c2047"></a>编译器错误 C2047

非法的 default

关键字 **`default`** 只能出现在 **`switch`** 语句中。

以下示例生成 C2047:

```cpp
// C2047.cpp
int main() {
   int i = 0;
   default:   // C2047
   switch(i) {
      case 0:
      break;
   }
}
```

可能的解决方法：

```cpp
// C2047b.cpp
int main() {
   int i = 0;
   switch(i) {
      case 0:
      break;
      default:
      break;
   }
}
```
