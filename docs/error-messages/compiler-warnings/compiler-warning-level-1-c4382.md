---
description: 了解详细信息：编译器警告 (等级 1) C4382
title: 编译器警告（等级 1）C4382
ms.date: 11/04/2016
f1_keywords:
- C4382
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
ms.openlocfilehash: 038225aea9592070b44af138be9deb5076e2f5f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311300"
---
# <a name="compiler-warning-level-1-c4382"></a>编译器警告（等级 1）C4382

> 引发 "*type*"：包含 __clrcall 析构函数或复制构造函数的类型只能在/clr： pure 模块中捕获

## <a name="remarks"></a>备注

**/Clr： pure** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

使用 **/clr** 进行编译时 (不是 **/clr： Pure**) ，异常处理要求本机类型中的成员函数 [__cdecl](../../cpp/cdecl.md) ，而不是 [__clrcall](../../cpp/clrcall.md)。 使用具有调用约定的成员函数的本机类型 `__clrcall` 无法在使用 **/clr** 编译的模块中被捕获。

如果将在使用 **/clr： pure** 编译的模块中捕获该异常，则可以忽略此警告。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="example"></a>示例

下面的示例生成 C4382。

```cpp
// C4382.cpp
// compile with: /clr /W1 /c
struct S {
   __clrcall ~S() {}
};

struct T {
   ~T() {}
};

int main() {
   S s;
   throw s;   // C4382

   S * ps = &s;
   throw ps;   // OK

   T t;
   throw t;   // OK
}
```
