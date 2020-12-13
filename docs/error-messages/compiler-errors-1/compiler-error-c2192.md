---
description: 了解更多：编译器错误 C2192
title: 编译器错误 C2192
ms.date: 11/04/2016
f1_keywords:
- C2192
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
ms.openlocfilehash: 02b1b5ace60d2b9a288cf933a43c5603b734eac7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337679"
---
# <a name="compiler-error-c2192"></a>编译器错误 C2192

参数 "number" 声明不同

第二次用不同的参数列表声明了 C 函数。 C 不支持重载函数。

下面的示例生成 C2192：

```c
// C2192.c
// compile with: /Za /c
void func( float, int );
void func( int, float );   // C2192, different parameter list
void func2( int, float );   // OK
```
