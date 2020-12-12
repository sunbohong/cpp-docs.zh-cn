---
description: 了解更多：编译器错误 C2661
title: 编译器错误 C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: 524d270fd15b529bad13a5ff1e5e46f3d5d9dd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170017"
---
# <a name="compiler-error-c2661"></a>编译器错误 C2661

"function"：没有重载函数使用数字参数

可能的原因：

1. 函数调用中的实参不正确。

1. 缺少函数声明。

下面的示例生成 C2661：

```cpp
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```
