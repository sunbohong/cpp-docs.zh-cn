---
description: 了解更多：编译器错误 C2085
title: 编译器错误 C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 2cd828c9a18c06c5794bef01ba861f702af2e096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252111"
---
# <a name="compiler-error-c2085"></a>编译器错误 C2085

"identifier"：不在形参表中

已在函数定义中声明该标识符，但在形参表中未声明。 仅 (ANSI C) 

下面的示例生成 C2085：

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

可能的解决方法：

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

缺少分号时， `func1()` 看起来像函数定义，而不是原型，因此 `main` 在内定义 `func1()` ，从而为标识符生成错误 C2085 `main` 。
