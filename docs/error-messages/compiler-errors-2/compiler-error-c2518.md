---
description: 了解更多：编译器错误 C2518
title: 编译器错误 C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: 1ebc270cd3544dc50d051677faeeec8e8e6bd979
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212722"
---
# <a name="compiler-error-c2518"></a>编译器错误 C2518

关键字 "关键字" 在基类列表中非法;掉

关键字 **`class`** 和 **`struct`** 不应出现在基类列表中。

下面的示例生成 C2518：

```cpp
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```
