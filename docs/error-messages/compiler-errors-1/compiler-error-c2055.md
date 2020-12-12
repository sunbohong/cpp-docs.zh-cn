---
description: 了解更多：编译器错误 C2055
title: 编译器错误 C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 0692488b8e1ea91fe235ade512c5fbe5094cdaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174931"
---
# <a name="compiler-error-c2055"></a>编译器错误 C2055

应输入形参表，而不是类型列表

函数定义包含参数类型列表，而不包含形参列表。 ANSI C 需要命名形参，除非它们是 void 或)  (省略号 `...` 。

下面的示例生成 C2055：

```c
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```
