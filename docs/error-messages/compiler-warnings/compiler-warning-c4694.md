---
description: 了解更多：编译器警告 C4694
title: 编译器警告 C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: f6a6890fab320c2471381076707eeca30ce3e99b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315070"
---
# <a name="compiler-warning-c4694"></a>编译器警告 C4694

> "*class*"：密封的抽象类不能有基类 "*base_class*"

一个抽象密封类不能继承自引用类型；一个密封抽象类既不能实现基类函数，也不能用作基类。

有关详细信息，请参阅 [抽象](../../extensions/abstract-cpp-component-extensions.md)、 [密封](../../extensions/sealed-cpp-component-extensions.md)以及 [类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md)。

此警告会自动提升为错误。 如果要修改此行为，请使用 [#pragma 警告](../../preprocessor/warning.md)。

## <a name="example"></a>示例

以下示例生成 C4694。

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```
