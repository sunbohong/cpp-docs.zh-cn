---
description: 了解更多：编译器错误 C3252
title: 编译器错误 C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: 59b5a0073d3dc8147b2e89d637fd98ba7339f6b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194301"
---
# <a name="compiler-error-c3252"></a>编译器错误 C3252

“method”：不能降低托管或 WinRT 类型中虚方法的可访问性

实现来自基类的虚方法或来自接口的任意方法的类不能减少该方法的访问。

请注意，接口中的所有方法都是公共的。

下列示例生成 C3252，并演示如何修复此错误：

```cpp
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```
