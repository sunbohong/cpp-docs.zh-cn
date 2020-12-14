---
description: 了解更多：编译器错误 C3609
title: 编译器错误 C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 187bc6d9849c385f6adb3ae2c25e2e90e7393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223121"
---
# <a name="compiler-error-c3609"></a>编译器错误 C3609

“成员”：密封的或最终函数必须是虚拟函数

仅对标记为的类、结构或成员函数允许使用 [sealed](../../extensions/sealed-cpp-component-extensions.md) 和 [final](../../cpp/final-specifier.md) 关键字 **`virtual`** 。

以下示例生成 C3609：

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
