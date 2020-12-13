---
description: 了解更多：编译器错误 C3744
title: 编译器错误 C3744
ms.date: 11/04/2016
f1_keywords:
- C3744
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
ms.openlocfilehash: 6d8e9184db37f65fd73a85aaaa6c350303802216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340224"
---
# <a name="compiler-error-c3744"></a>编译器错误 C3744

对于托管事件，__unhook 必须具有至少3个参数

[`__unhook`](../../cpp/unhook.md)函数在为 Managed Extensions for C++ 编译的程序中使用时必须采用三个参数。

**`__hook`** 和与 **`__unhook`** 编程不兼容 **`/clr`** 。 改为使用 + = 和-= 运算符。

只能使用过时的编译器选项访问 C3744 **`/clr:oldSyntax`** 。
