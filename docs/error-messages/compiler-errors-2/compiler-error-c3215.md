---
description: 了解更多：编译器错误 C3215
title: 编译器错误 C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 1291f480e4f01502db4232585f7e7786fd637072
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173735"
---
# <a name="compiler-error-c3215"></a>编译器错误 C3215

“type1”: 泛型类型参数已由“type2”进行约束

已多次指定约束。

有关泛型的详细信息，请参阅 [Generics](../../extensions/generics-cpp-component-extensions.md)。

下面的示例生成 C3215：

```cpp
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

可能的解决方法：

```cpp
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```
