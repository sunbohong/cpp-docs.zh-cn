---
description: 了解更多：编译器错误 C3890
title: 编译器错误 C3890
ms.date: 11/04/2016
f1_keywords:
- C3890
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
ms.openlocfilehash: 1eddf71c5b380f97cd9910649f64fc67045b76a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274289"
---
# <a name="compiler-error-c3890"></a>编译器错误 C3890

"var"：不能采用 literal 数据成员的地址

原义数据成员存在于垃圾回收堆中。  可以移动垃圾回收堆上的对象，因此获取地址并不有用。

下面的示例生成 C3890：

```cpp
// C3890.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   int p = &Y1::staticConst;   // C3890
   int p2 = Y1::staticConst;   // OK
}
```
