---
description: 了解更多：编译器错误 C2272
title: 编译器错误 C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 5a46c68a09eaec9fc33ef4eaa64afaebea411659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336248"
---
# <a name="compiler-error-c2272"></a>编译器错误 C2272

"function"：静态成员函数上不允许使用修饰符

**`static`** 成员函数由内存模型说明符（如 [const](../../cpp/const-cpp.md)或 [volatile](../../cpp/volatile-cpp.md)）声明，而成员函数不允许使用此类修饰符 **`static`** 。

下面的示例生成 C2272：

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
