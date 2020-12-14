---
description: 了解更多：编译器错误 C2500
title: 编译器错误 C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: 39d1ab0876470b443d4444a3c583cc0993c98325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275966"
---
# <a name="compiler-error-c2500"></a>编译器错误 C2500

"identifier1"： "identifier2" 已是直接基类

某个类或结构在基类列表中出现多次。

直接基是基列表中提到的一个。 间接基是基列表中某个类的基类。

不能将一个类多次指定为直接基类。 类可以多次用作间接基类。

下面的示例生成 C2500：

```cpp
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```
