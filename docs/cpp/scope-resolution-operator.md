---
title: 作用域解析运算符： `::`
description: 了解范围解析运算符 `::` 在标准 c + + 中的工作方式。
ms.date: 12/06/2020
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.openlocfilehash: ff774d9fcca9f68cb2925af82c55ef438ab4d71a
ms.sourcegitcommit: 7b131db4ed39bddb4a456ebea402f47c5cbd69d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96776526"
---
# <a name="scope-resolution-operator-"></a>作用域解析运算符： `::`

范围解析运算符 **`::`** 用于标识和消除在不同范围内使用的标识符。 有关作用域的详细信息，请参阅 [作用域](../cpp/scope-visual-cpp.md)。

## <a name="syntax"></a>语法

> *`qualified-id`*:\
> &emsp; *`nested-name-specifier`* **`template`** <sub>opt</sub> *`unqualified-id`*

> *`nested-name-specifier`*:\
> &emsp;**`::`**\
> &emsp;*`type-name`* **`::`**\
> &emsp;*`namespace-name`* **`::`**\
> &emsp;*`decltype-specifier`* **`::`**\
> &emsp;*`nested-name-specifier`* *`identifier`* **`::`**\
> &emsp;*`nested-name-specifier`***`template`** <sub>opt</sub> opt *`simple-template-id`***`::`**

> *`unqualified-id`*:\
> &emsp;*`identifier`*\
> &emsp;*`operator-function-id`*\
> &emsp;*`conversion-function-id`*\
> &emsp;*`literal-operator-id`*\
> &emsp;**`~`** *`type-name`*\
> &emsp;**`~`** *`decltype-specifier`*\
> &emsp;*`template-id`*

## <a name="remarks"></a>备注

`identifier` 可以是变量、函数或枚举值。

## <a name="use--for-classes-and-namespaces"></a>用于 `::` 类和命名空间

以下示例显示范围解析运算符如何与命名空间和类一起使用：

```cpp
namespace NamespaceA{
    int x;
    class ClassA {
    public:
        int x;
    };
}

int main() {

    // A namespace name used to disambiguate
    NamespaceA::x = 1;

    // A class name used to disambiguate
    NamespaceA::ClassA a1;
    a1.x = 2;
}
```

没有范围限定符的范围解析运算符表示全局命名空间。

```cpp
namespace NamespaceA{
    int x;
}

int x;

int main() {
    int x;

    // the x in main()
    x = 0;
    // The x in the global namespace
    ::x = 1;

    // The x in the A namespace
    NamespaceA::x = 2;
}
```

可以使用范围解析运算符标识的成员 **`namespace`** ，或标识在指令中 nominates 成员的命名空间的命名空间 **`using`** 。 在下面的示例中，你可以使用 `NamespaceC` 来限定 `ClassB` ，即使 `ClassB` 是在命名空间中声明的， `NamespaceB` 因为 `NamespaceB` 是 `NamespaceC` 由指令在中命名的 **`using`** 。

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace NamespaceB;
}

int main() {
    NamespaceB::ClassB b_b;
    NamespaceC::ClassB c_b;

    b_b.x = 3;
    c_b.x = 4;
}
```

可使用范围解析运算符链。 在以下示例中，`NamespaceD::NamespaceD1` 将标识嵌套的命名空间 `NamespaceD1`，并且 `NamespaceE::ClassE::ClassE1` 将标识嵌套的类 `ClassE1`。

```cpp
namespace NamespaceD{
    namespace NamespaceD1{
        int x;
    }
}

namespace NamespaceE{
    class ClassE{
    public:
        class ClassE1{
        public:
            int x;
        };
    };
}

int main() {
    NamespaceD:: NamespaceD1::x = 6;
    NamespaceE::ClassE::ClassE1 e1;
    e1.x = 7  ;
}
```

## <a name="use--for-static-members"></a>用于 `::` 静态成员

必须使用范围解析运算符来调用类的静态成员。

```cpp
class ClassG {
public:
    static int get_x() { return x;}
    static int x;
};

int ClassG::x = 6;

int main() {

    int gx1 = ClassG::x;
    int gx2 = ClassG::get_x();
}
```

## <a name="use--for-scoped-enumerations"></a>用于 `::` 作用域枚举

作用域内的解析运算符也与范围枚举 [枚举声明](../cpp/enumerations-cpp.md)的值一起使用，如以下示例中所示：

```cpp
enum class EnumA{
    First,
    Second,
    Third
};

int main() {
    EnumA enum_value = EnumA::First;
}
```

## <a name="see-also"></a>请参阅

[C + + 内置运算符、优先级和结合性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[命名空间](../cpp/namespaces-cpp.md)
