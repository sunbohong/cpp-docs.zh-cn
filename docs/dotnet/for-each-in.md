---
title: for each, in
description: 每个的 c + +/CLI，在语句说明和示例中。
ms.date: 09/25/2020
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: 7f228a773dfcbe791e26ea3e1bd8cfba7f3ab028
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413914"
---
# <a name="for-each-in"></a>for each, in

通过数组或集合迭代。 此非标准关键字在 C++/CLI 和本机 C++ 项目中可用。 但是，不建议使用它。 请考虑使用 [基于标准范围的 For 语句 (c + +) ](../cpp/range-based-for-statement-cpp.md) 。

## <a name="all-runtimes"></a>所有运行时

### <a name="syntax"></a>语法

> 对于*表达式***中****的每个 (** *类型**标识符* **) {**\
> &nbsp;&nbsp;&nbsp;&nbsp;*前瞻性*\
> **}**

### <a name="parameters"></a>参数

type<br/>
`identifier` 的类型。

*identifier*<br/>
代表集合元素的迭代变量。  当 `identifier` 是 [跟踪引用运算符](../extensions/tracking-reference-operator-cpp-component-extensions.md)时，可以修改元素。

*expression*<br/>
数组表达式或集合。 集合元素必须让编译器能将其转换为 `identifier` 类型。

*前瞻性*<br/>
要执行的一个或多个语句。

### <a name="remarks"></a>备注

`for each` 语句用于循环访问集合。 您可以修改集合中的元素，但不能添加或删除元素。

对数组或集合中的每个元素执行这些 *语句* 。 为集合中的所有元素完成迭代后，控制将传递给 `for each` 块之后的语句。

`for each` 和 `in` 是 [上下文相关的关键字](../extensions/context-sensitive-keywords-cpp-component-extensions.md)。

## <a name="windows-runtime"></a>Windows 运行时

### <a name="requirements"></a>要求

编译器选项： **/ZW**

### <a name="example"></a>示例

本示例演示了如何使用 `for each` 来循环访问字符串。

```cpp
// for_each_string1.cpp
// compile with: /ZW
#include <stdio.h>
using namespace Platform;

ref struct MyClass {
   property String^ MyStringProperty;
};

int main() {
   String^ MyString = ref new String("abcd");

   for each ( char c in MyString )
      wprintf("%c", c);

   wprintf("/n");

   MyClass^ x = ref new MyClass();
   x->MyStringProperty = "Testing";

   for each( char c in x->MyStringProperty )
      wprintf("%c", c);
}
```

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>公共语言运行时

### <a name="remarks"></a>备注

CLR 语法与 **所有运行时** 语法相同，但以下情况除外。

*expression*<br/>
托管的数组表达式或集合。 集合元素必须是，以便编译器可以将其转换 <xref:System.Object> 为 *标识符* 类型。

*expression* 的计算结果为实现、的类型， <xref:System.Collections.IEnumerable> <xref:System.Collections.Generic.IEnumerable%601> 或定义方法的类型，该 `GetEnumerator` 方法返回实现 <xref:System.Collections.IEnumerator> 或声明中定义的所有方法的类型 `IEnumerator` 。

### <a name="requirements"></a>要求

编译器选项： **/clr**

### <a name="example"></a>示例

本示例演示了如何使用 `for each` 来循环访问字符串。

```cpp
// for_each_string2.cpp
// compile with: /clr
using namespace System;

ref struct MyClass {
   property String ^ MyStringProperty;
};

int main() {
   String ^ MyString = gcnew String("abcd");

   for each ( Char c in MyString )
      Console::Write(c);

   Console::WriteLine();

   MyClass ^ x = gcnew MyClass();
   x->MyStringProperty = "Testing";

   for each( Char c in x->MyStringProperty )
      Console::Write(c);
}
```

```Output
abcd

Testing
```

## <a name="see-also"></a>另请参阅

[运行时平台的组件扩展](../extensions/component-extensions-for-runtime-platforms.md)\
[基于范围的 for 语句 (c + +) ](../cpp/range-based-for-statement-cpp.md)
