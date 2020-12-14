---
description: 了解更多：编译器错误 C3163
title: 编译器错误 C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 53d0135e3083de7727b2a6c7f51a3f75e7314405
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203947"
---
# <a name="compiler-error-c3163"></a>编译器错误 C3163

> "*构造*"：特性与以前的声明不一致

应用于定义的属性 (s) 与应用于声明的)  (属性冲突。

解决 C3163 的一种方法是消除前向声明中的特性。 前向声明中的任何特性都应小于定义上的特性，或在最大程度上等于它们。

C3163 错误的可能原因包括 Microsoft 源代码批注语言 (SAL) 。 如果使用标志编译项目，则 SAL 宏将不会展开 **`/analyze`** 。 **`/analyze`** 如果你尝试使用选项重新编译，则在不进行编译的情况下，不会引发 C3163 的程序 **`/analyze`** 。 有关 SAL 的详细信息，请参阅 [Sal 注释](../../c-runtime-library/sal-annotations.md)。

## <a name="example"></a>示例

下面的示例生成 C3163。

```cpp
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>请参阅

[SAL 批注](../../c-runtime-library/sal-annotations.md)
