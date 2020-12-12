---
description: 了解更多：编译器错误 C3068
title: 编译器错误 C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: a73c525f017a3d571600e31d4c9ea875d0b25662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281666"
---
# <a name="compiler-error-c3068"></a>编译器错误 C3068

"function"： "naked" 函数不能包含在出现 c + + 异常时需要展开的对象

编译器无法对引发异常的 [裸](../../cpp/naked-cpp.md) 函数执行堆栈展开，因为在函数中创建了临时对象，但指定了 ([/Ehsc](../../build/reference/eh-exception-handling-model.md)) 的 c + + 异常处理。

若要解决此错误，请至少执行下列操作之一：

- 不要用/EHsc. 编译

- 不要将函数标记为 `naked` 。

- 不要在函数中创建临时对象。

如果函数在堆栈上创建临时对象，则如果函数引发异常，并且如果启用 c + + 异常处理，则编译器将在引发异常时清理堆栈。

当引发异常时，将对函数执行编译器生成的代码，该代码称为 prolog 和 epilog，而在裸函数中不存在。

## <a name="example"></a>示例

下面的示例生成 C3068：

```cpp
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```
