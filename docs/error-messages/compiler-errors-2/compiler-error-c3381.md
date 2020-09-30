---
title: 编译器错误 C3381
description: Microsoft c + + 编译器错误 C3381，其原因和解决方法。
ms.date: 09/28/2020
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: 48a6c81f9506c532333b5353b8b194d17c91043f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510146"
---
# <a name="compiler-error-c3381"></a>编译器错误 C3381

> "*identifier*"：程序集访问说明符仅可用于使用/clr 选项编译的代码中

类型是使用访问说明符声明或定义的，只允许在使用编译的代码中使用 **`/clr`** 。

## <a name="remarks"></a>注解

此错误可能是由于位置错误的 **`public`** 、或 **`protected`** **`private`** 关键字，或在 **`:`** 或中的访问说明符后) 缺少冒号 (**`class`** **`struct`** 。

在 c + +/CLI 中，本机类型在程序集外可见，但你只能在编译中指定本机类型的程序集访问权限 **`/clr`** 。 有关详细信息，请参阅[类型可见性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)和[ `/clr` (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="example"></a>示例

下面的示例生成 C3381。 若要修复此问题，请首先 **`public`** 从 `class A` 定义中删除说明符，或使用选项编译 **`/clr`** 。 接下来，在后面添加一个冒号， **`private`** 以指定对的访问权限 `class B {} b;` 。 这是因为嵌套类不能将程序集访问说明符作为声明的一部分。

```cpp
// C3381.cpp
// compile with: /c
public class A {   // C3381
    private class B {} b;   // C3381
};
```
