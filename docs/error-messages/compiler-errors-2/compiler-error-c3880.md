---
description: 了解更多：编译器错误 C3880
title: 编译器错误 C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: c2d279cd50716f647fbbdf51f9f9c39863d4e2d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274588"
---
# <a name="compiler-error-c3880"></a>编译器错误 C3880

"var"：不能是 literal 数据成员

[文本](../../extensions/literal-cpp-component-extensions.md)属性的类型必须为或可转换为以下类型之一：

- 整型类型

- 字符串

- 具有整型或基础类型的枚举

下面的示例生成 C3880：

```cpp
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```
