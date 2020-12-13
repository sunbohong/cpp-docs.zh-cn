---
description: 了解详细信息：编译器警告 (等级 1) C4342
title: 编译器警告（等级 1）C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: f08cf24b0fe429e8b788a20fbcb05d2a8cd8b1d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340015"
---
# <a name="compiler-warning-level-1-c4342"></a>编译器警告（等级 1）C4342

行为更改：调用了 "*function*"，但在以前的版本中调用了成员运算符

在 Visual Studio 2002 之前的 Visual C++ 版本中，调用了一个成员，但此行为已更改，并且编译器现在在命名空间范围内找到最佳匹配项。

如果找到了成员运算符，则编译器之前不会考虑任何命名空间范围运算符。 如果命名空间范围内有更好的匹配项，则当前编译器会正确调用它，而以前的编译器不会将其视为。

成功将代码移植到最新版本后，应禁用此警告。  编译器可能会发出误报，并为没有行为更改的代码生成此警告。

默认情况下，此警告处于关闭状态。 有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

下面的示例生成 C4342：

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```
