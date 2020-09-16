---
title: 编译器警告（等级 1）C4835
ms.date: 11/04/2016
f1_keywords:
- C4835
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
ms.openlocfilehash: a298eb0c55f96289a0043f3a996b09798745c92d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684217"
---
# <a name="compiler-warning-level-1-c4835"></a>编译器警告（等级 1）C4835

"variable"：在主机程序集中首次执行托管代码时，导出数据的初始值设定项将不会运行

访问托管组件之间的数据时，建议不要使用本机 c + + 导入和导出机制。 相反，请在托管类型内声明数据成员，并 `#using` 在客户端中引用元数据。 有关详细信息，请参阅 [#using 指令](../../preprocessor/hash-using-directive-cpp.md)。

## <a name="examples"></a>示例

下面的示例生成 C4835。

```cpp
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

下面的示例使用上一示例中生成的组件，并显示变量的值与预期不符。

```cpp
// C4835_b.cpp
// compile with: /clr C4835.lib
#include <stdio.h>
__declspec(dllimport) int m;
__declspec(dllimport) int *p;

int main() {
   printf("%d\n", m);
   printf("%d\n", p);
}
```

```Output
0
268456008
```
