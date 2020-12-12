---
description: 了解更多：编译器错误 C3062
title: 编译器错误 C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: b57d03f3ef09e1d01741866d99dfff87aa5aa28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281738"
---
# <a name="compiler-error-c3062"></a>编译器错误 C3062

"enum"：枚举器需要值，因为基础类型是 "type"

可以指定枚举的基础类型。 但是，某些类型要求向每个枚举器分配值。

有关枚举的详细信息，请参阅 [enum 类](../../extensions/enum-class-cpp-component-extensions.md)。

下面的示例生成 C3062：

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
