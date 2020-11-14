---
title: 类型限定符
description: 介绍 Microsoft Visual C 编译器中使用的 C 语言的类型限定符
ms.date: 11/6/2020
helpviewer_keywords:
- volatile keyword [C], type qualifier
- type qualifiers
- volatile keyword [C]
- qualifiers for types
- const keyword [C]
- memory, access using volatile
- volatile keyword [C], type specifier
ms.assetid: bb4c6744-1dd7-40a8-b4eb-f5585be30908
ms.openlocfilehash: dd36aeb5d142eebbd6e4a339fe6c18925a6fd45a
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381605"
---
# <a name="type-qualifiers"></a>类型限定符

类型限定符为标识符提供两个属性之一。 `const` 类型限定符将对象声明为不可修改。 `volatile` 类型限定符声明了一个项，此项的值可以被超出此项所在程序的控制范围的某个项（如并发执行的线程）以合法方式更改。

`const`、`restrict` 和 `volatile` 这几个类型限定符只能在声明中出现一次。 类型限定符可与任何类型说明符一起出现；但是，它们不能在多项声明中的第一个逗号的后面出现。 例如，以下声明是合法的：

```c
typedef volatile int VI;
const int ci;
```

以下声明是非法的：

```c
typedef int *i, volatile *vi;
float f, const cf;
```

仅当访问作为表达式的左值的标识符时，类型限定符才会相关。 有关左值和表达式的信息，请参阅[左值表达式和右值表达式](../c-language/l-value-and-r-value-expressions.md)。

## <a name="syntax"></a>语法

*`type-qualifier`* :\
&emsp;**`const`**\
&emsp;**`restrict`**\
&emsp;**`volatile`**

## <a name="const-and-volatile"></a>`const` 和 `volatile`

以下是合法的 `const` 和 `volatile` 声明：

```c
int const *p_ci;      // Pointer to constant int
int const (*p_ci);   // Pointer to constant int
int *const cp_i;     // Constant pointer to int
int (*const cp_i);   // Constant pointer to int
int volatile vint;     // Volatile integer
```

如果数组类型的规范包括类型限定符，则将限定元素而不是数组类型。 如果函数类型的规范包括限定符，则行为是不确定的。 `volatile` 和 `const` 都不会影响值的范围或对象的算术属性。

- `const` 关键字可用于修改任何基本或聚合类型，或修改指向任何类型的对象的指针或 `typedef`。 如果某项声明为只包含 `const` 类型限定符，则其类型被视为 const int。`const` 变量可以被初始化，也可以被置于存储的只读区域中。 `const` 关键字对于声明指向 `const` 的指针很有用，因为这要求函数不以任何方式更改指针。

- 编译器假定，在程序运行的任何时刻，使用或修改 `volatile` 变量的值的未知进程都可以访问此变量。 无论在命令行上指定了哪些优化，都必须为 `volatile` 变量的每次赋值或引用生成代码，即使它看起来没有任何效果。

如果单独使用 `volatile`，则假定为 `int`。 `volatile` 类型说明符可用于提供对特殊内存位置的可靠访问。 将 `volatile` 用于数据对象，这些对象可能会被信号处理程序、并行执行的程序或特殊硬件（如内存映射的 I/O 控制寄存器）访问或更改。 可以将变量在其生存期内声明为 `volatile`，也可以将单个引用强制转换为 `volatile`。

- 一个项可以同时是 `const` 和 `volatile`，在这种情况下，此项不能被它自己的程序以合法方式修改，但能被一些异步进程修改。
 
## `restrict`

C99 中引入的 `restrict` 类型限定符可应用于指针声明。 它限定指针，而不是它指向的内容。

`restrict` 是编译器的优化提示，当前作用域中没有其他指针引用相同的内存位置。 也就是说，只使用指针或从其派生的值（例如指针 + 1）在指针的生存期内访问对象。 这有助于编译器生成更多的优化代码。 C++ 具有等效机制 [`__restrict`](../cpp/extension-restrict.md)

请注意，`restrict` 是你与编译器之间的协定。 如果你对标记为 `restrict` 的指针使用了别名，则结果是不确定的。

下面是使用 `restrict` 的示例：

```c
void test(int* restrict first, int* restrict second, int* val)
{
    *first += *val;
    *second += *val;
}

int main()
{
    int i = 1, j = 2, k = 3;
    test(&i, &j, &k);

    return 0;
}

// Marking union members restrict tells the compiler that
// only z.x or z.y will be accessed in any scope, which allows
// the compiler to optimize access to the members.
union z 
{
    int* restrict x;
    double* restrict y;
};
```

## <a name="see-also"></a>另请参阅

[`/std`（指定语言标准版本）](../build/reference/std-specify-language-standard-version.md)\
[声明和类型](../c-language/declarations-and-types.md)
