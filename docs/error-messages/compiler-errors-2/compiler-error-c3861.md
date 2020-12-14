---
description: 了解更多：编译器错误 C3861
title: 编译器错误 C3861
ms.date: 03/23/2018
f1_keywords:
- C3861
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
ms.openlocfilehash: bba259496de09e86b59f9cad1ac1bf89a697a1da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222900"
---
# <a name="compiler-error-c3861"></a>编译器错误 C3861

> "*identifier*"：找不到标识符

即使使用自变量相关的查找，编译器也无法解析对标识符的引用。

## <a name="remarks"></a>备注

若要修复此错误，请将 *标识符* 的使用与标识符声明进行比较以区分大小写和拼写。 验证是否正确使用了[作用域解析运算符](../../cpp/scope-resolution-operator.md)[和命名空间](../../cpp/namespaces-cpp.md#using_directives)。 如果在标头文件中声明了标识符，请在引用标识符之前验证标头是否已包含。 如果标识符应在外部可见，请确保在使用该标识符的任何源文件中声明该标识符。 还要检查标识符声明或定义是否未被 [条件编译指令](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)排除。

从 Visual Studio 2015 中的 C 运行库中删除过时函数的更改可能导致 C3861。 若要解决此错误，请删除对这些函数的引用或将其替换为安全替代项（如果有）。 有关详细信息，请参阅 [过时函数](../../c-runtime-library/obsolete-functions.md)。

如果从较旧版本的编译器中的项目迁移之后出现错误 C3861，则可能存在与支持的 Windows 版本相关的问题。 Visual C++ 不再支持面向 Windows 95、Windows 98、Windows ME、Windows NT 或 Windows 2000。 如果你的 **WINVER** 或 **_WIN32_WINNT** 宏分配给了这些 Windows 版本中的一个，则必须修改宏。 有关详细信息，请参阅 [修改 WINVER 和 _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md)。

## <a name="examples"></a>示例

### <a name="undefined-identifier"></a>未定义标识符

下面的示例生成 C3861，因为未定义标识符。

```cpp
// C3861.cpp
void f2(){}
int main() {
   f();    // C3861
   f2();   // OK
}
```

### <a name="identifier-not-in-scope"></a>标识符不在范围内

下面的示例生成 C3861，因为标识符仅在其定义的文件作用域中可见，除非它在使用它的其他源文件中声明。

```cpp
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {
   std::cout << f() << std::endl;    // C3861
}
```

```cpp
// C3861_a2.cpp
int f() {  // declared and defined here
   return 42;
}
```

### <a name="namespace-qualification-required"></a>需要命名空间限定

C + + 标准库中的异常类需要 `std` 命名空间。

```cpp
// C3861_b.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   try {
      throw exception("Exception");   // C3861
      // try the following line instead
      // throw std::exception("Exception");
   }
   catch (...) {
      std::cout << "caught an exception" << std::endl;
   }
}
```

### <a name="obsolete-function-called"></a>已过时的函数

已从 CRT 库中删除过时的函数。

```cpp
// C3861_c.cpp
#include <stdio.h>
int main() {
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C3861
   // Use gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

### <a name="adl-and-friend-functions"></a>ADL 和友元函数

下面的示例生成 C3767，因为编译器不能对使用参数依赖查找 `FriendFunc` ：

```cpp
namespace N {
   class C {
      friend void FriendFunc() {}
      friend void AnotherFriendFunc(C* c) {}
   };
}

int main() {
   using namespace N;
   FriendFunc();   // C3861 error
   C* pC = new C();
   AnotherFriendFunc(pC);   // found via argument-dependent lookup
}
```

若要修复此错误，请在类范围中声明友元，并在命名空间范围中定义它：

```cpp
class MyClass {
   int m_private;
   friend void func();
};

void func() {
   MyClass s;
   s.m_private = 0;
}

int main() {
   func();
}
```
