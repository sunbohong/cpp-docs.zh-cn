---
title: 一般选择 (C11)
description: 介绍 Microsoft Visual C 编译器中使用的 C11 _Generic 关键字
ms.date: 12/9/2020
helpviewer_keywords:
- _Generic keyword [C]
ms.openlocfilehash: de0e840c19186219d53800b9d008d7695b807bc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97348891"
---
# <a name="generic-selection-c11"></a>一般选择 (C11)

使用 `_Generic` 关键字编写代码，该代码根据参数的类型在编译时选择表达式。 在 C++ 中重载时，相似的是参数类型选择要调用的函数，不同的是参数类型选择要计算的表达式。

例如，表达式 `_Generic(42, int: "integer", char: "character", default: "unknown");` 计算 `42` 的类型，并在列表中查找匹配类型 `int`。 它找到该匹配类型并返回 `"integer"`。

## <a name="syntax"></a>语法

*`generic-selection`*:\
&nbsp;&nbsp;&nbsp;&nbsp;**`_Generic`** **(** *`assignment-expression`, `assoc-list`* **)**

*`assoc-list`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`association`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`assoc-list`, `association`*

*`association`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`type-name`* : *`assignment-expression`*\
&nbsp;&nbsp;&nbsp;&nbsp;**`default`** : *`assignment-expression`*

第一个 `assignment-expression` 称为控制表达式。 控制表达式的类型在编译时确定，并与 `assoc-list` 匹配，以查找要计算和返回的表达式。 不会计算控制表达式。 例如，`_Generic(intFunc(), int: "integer", default: "error");` 不会在运行时调用 `intFunc()`。 

确定控制表达式的类型后，会在与 `assoc-list` 匹配之前删除 `const`、`volatile` 和 `restrict`。

不会计算 `assoc-list` 中未选择的条目。

## <a name="constraints"></a>约束

- `assoc-list` 不能多次指定同一类型。
- `assoc-list` 不能指定彼此兼容的类型，例如枚举和该枚举的基础类型。
- 如果一般选择没有默认值，则控制表达式在通用关联列表中必须只有一个兼容的类型名称。

## <a name="example"></a>示例

使用 `_Generic` 的一种方法是在宏中。 <tgmath.h> 标头文件使用 _Generic 来根据参数的类型调用正确的数学函数。 例如，`cos()` 的宏将带有浮点的调用映射到 `cosf()`，同时将带有复杂双精度的调用映射到 `ccos()`。

下面的示例演示如何编写可标识传递给它的参数的类型的宏。 如果 `assoc-list` 中没有匹配控制表达式的条目，则会生成 `"unknown"`：

```C
// Compile with /std:c11

#include <stdio.h>

/* Get a type name string for the argument x */
#define TYPE_NAME(X) _Generic((X), \
      int: "int", \
      char: "char", \
      double: "double", \
      default: "unknown")

int main()
{
    printf("Type name: %s\n", TYPE_NAME(42.42));

    // The following would result in a compile error because 
    // 42.4 is a double, doesn't match anything in the list, 
    // and there is no default.
    // _Generic(42.4, int: "integer", char: "character"));
}

/* Output:
Type name: double
*/

```

## <a name="see-also"></a>另请参阅

[`/std`（指定语言标准版本）](../build/reference/std-specify-language-standard-version.md)\
[泛型类型数学](../c-runtime-library/tgmath.md)