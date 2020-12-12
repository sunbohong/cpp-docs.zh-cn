---
description: 了解更多：编译器错误 C2666
title: 编译器错误 C2666
ms.date: 11/04/2016
f1_keywords:
- C2666
helpviewer_keywords:
- C2666
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
ms.openlocfilehash: bfee8a2cb62f351d7d09faa499f1a936d14ea813
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210811"
---
# <a name="compiler-error-c2666"></a>编译器错误 C2666

"identifier"：数字重载具有相似的转换

重载的函数或运算符不明确。   形参列表可能太类似，编译器无法解析多义性。  若要解决此错误，请显式转换一个或多个实际参数。

## <a name="examples"></a>示例

下面的示例生成 C2666：

```cpp
// C2666.cpp
struct complex {
   complex(double);
};

void h(int,complex);
void h(double, double);

int main() {
   h(3,4);   // C2666
}
```

此错误还可能是由于对 Visual Studio .NET 2003 执行的编译器一致性工作引起的：

- 二元运算符和用户定义的到指针类型的转换

- 限定转换不同于标识转换

对于二元运算符 \<, > ， \<=, and > =，如果参数的类型定义了用户定义的转换运算符来转换为操作数的类型，则传递的参数现在会隐式转换为操作数的类型。 现在可能存在歧义。

对于在 Visual Studio .NET 2003 和 Visual Studio .NET 版本的 Visual C++ 中都有效的代码，请使用函数语法显式调用类运算符。

```cpp
// C2666b.cpp
#include <string.h>
#include <stdio.h>

struct T
{
    T( const T& copy )
    {
        m_str = copy.m_str;
    }

    T( const char* str )
    {
        int iSize = (strlen( str )+ 1);
        m_str = new char[ iSize ];
        if (m_str)
            strcpy_s( m_str, iSize, str );
    }

    bool operator<( const T& RHS )
    {
        return m_str < RHS.m_str;
    }

    operator char*() const
    {
        return m_str;
    }

    char* m_str;
};

int main()
{
    T str1( "ABCD" );
    const char* str2 = "DEFG";

    // Error - Ambiguous call to operator<()
    // Trying to convert str1 to char* and then call
    // operator<( const char*, const char* )?
    //  OR
    // trying to convert str2 to T and then call
    // T::operator<( const T& )?

    if( str1 < str2 )   // C2666

    if ( str1.operator < ( str2 ) )   // Treat str2 as type T
        printf_s("str1.operator < ( str2 )\n");

    if ( str1.operator char*() < str2 )   // Treat str1 as type char*
        printf_s("str1.operator char*() < str2\n");
}
```

下面的示例生成 C2666

```cpp
// C2666c.cpp
// compile with: /c

enum E
{
    E_A,   E_B
};

class A
{
    int h(const E e) const {return 0; }
    int h(const int i) { return 1; }
    // Uncomment the following line to resolve.
    // int h(const E e) { return 0; }

    void Test()
    {
        h(E_A);   // C2666
        h((const int) E_A);
        h((int) E_A);
    }
};
```
