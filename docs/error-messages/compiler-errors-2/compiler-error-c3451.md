---
description: 了解更多：编译器错误 C3451
title: 编译器错误 C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: a5cc37bf273474553c375edc940d160f0c1d023d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316000"
---
# <a name="compiler-error-c3451"></a>编译器错误 C3451

"attribute"：不能将非托管特性应用于 "type"

C + + 特性不能应用于 CLR 类型。 有关详细信息，请参阅 [c + + 特性参考](../../windows/attributes/attributes-alphabetical-reference.md) 。

有关详细信息，请参阅 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)。

此错误可能是由于对 Visual Studio 2005 执行的编译器一致性工作引起的：使用 CLR 编程在用户定义的属性上不再允许 [uuid](../../windows/attributes/uuid-cpp-attributes.md) 特性。 请改用 <xref:System.Runtime.InteropServices.GuidAttribute>。

## <a name="example"></a>示例

下面的示例生成 C3451。

```cpp
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```
