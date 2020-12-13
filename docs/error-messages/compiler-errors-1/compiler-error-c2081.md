---
description: 了解更多：编译器错误 C2081
title: 编译器错误 C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: e6f75d6d478d9523d36a9671457cf2a5618e4f21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151172"
---
# <a name="compiler-error-c2081"></a>编译器错误 C2081

"identifier"：形参表中的名称非法

标识符导致语法错误。

此错误的原因可能是使用了形参表的旧样式。 必须在形参表中指定形参的类型。

下面的示例生成 C2081：

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

可能的解决方法：

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```
