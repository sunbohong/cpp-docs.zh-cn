---
description: 了解详细信息：编译器警告 (等级 1) C4297
title: 编译器警告（等级 1）C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: ef330302702ee9e7a8fa55128a6f1f61732552f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311729"
---
# <a name="compiler-warning-level-1-c4297"></a>编译器警告（等级 1）C4297

“function”: 假定函数不引发异常，但确实发生了异常

函数声明包含 (可能隐式) **`noexcept`** 说明符、空 **`throw`** 异常说明符或 [__declspec (nothrow)](../../cpp/nothrow-cpp.md) 特性，并且定义包含一个或多个 [throw](../../cpp/try-throw-and-catch-statements-cpp.md) 语句。 若要解决 C4297，请不要尝试在声明了 `__declspec(nothrow)`、`noexcept(true)` 或 `throw()` 的函数中引发异常。 或者，删除 **`noexcept`** 、 `throw()` 或 `__declspec(nothrow)` 规范。

默认情况下，编译器为用户定义的析构函数和释放函数以及编译器生成的特殊成员函数生成隐式 `noexcept(true)` 说明符。 这符合 ISO C++ 11 标准。 若要阻止生成隐式 noexcept 说明符并将编译器恢复 Visual Studio 2013 的非标准行为，请使用 **/zc： implicitNoexcept** 选项。 有关详细信息，请参阅 [/zc： implicitNoexcept (隐式异常说明符) ](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md)。

有关异常规范的详细信息，请参阅 [异常规范 (throw) ](../../cpp/exception-specifications-throw-cpp.md)。 有关如何在编译时修改异常处理行为的信息，请参阅 [/EH (异常处理模型) ](../../build/reference/eh-exception-handling-model.md) 。

对于标记为 extern "C" 的 __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) 函数，也会生成此警告，即使这些函数是 c + + 函数也是如此。

下面的示例生成 C4297：

```cpp
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```
