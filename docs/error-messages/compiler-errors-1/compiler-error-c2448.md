---
description: 了解更多：编译器错误 C2448
title: 编译器错误 C2448
ms.date: 11/04/2016
f1_keywords:
- C2448
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
ms.openlocfilehash: 8dc6f794a71c89b4b14d0a3f33d5617e296b3dc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189608"
---
# <a name="compiler-error-c2448"></a>编译器错误 C2448

"identifier"：函数样式初始值设定项显示为函数定义

函数定义不正确。

此错误可能由旧式 C 语言形式列表引起。

下面的示例生成 C2448：

```cpp
// C2448.cpp
void func(c)
   int c;
{}   // C2448
```
