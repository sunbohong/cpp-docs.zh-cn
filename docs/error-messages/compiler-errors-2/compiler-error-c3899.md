---
description: 了解更多：编译器错误 C3899
title: 编译器错误 C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 04d8af9427d868b0890899d295f3aa6f678eafce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260041"
---
# <a name="compiler-error-c3899"></a>编译器错误 C3899

"var"： initonly 数据成员的左值不允许直接在类 "class" 中的并行区域内使用

[Initonly (c + +/cli) ](../../dotnet/initonly-cpp-cli.md)数据成员不能在位于[并行](../../parallel/openmp/reference/openmp-directives.md#parallel)区域中的构造函数的该部分内初始化。  这是因为编译器会执行该代码的内部重定位，因此它实际上不再是构造函数的一部分。

若要解决此问题，请在构造函数中初始化 initonly 数据成员，但在并行区域外初始化。

## <a name="example"></a>示例

下面的示例生成 C3899。

```cpp
// C3899.cpp
// compile with: /clr /openmp
#include <omp.h>

public ref struct R {
   initonly int x;
   R() {
      x = omp_get_thread_num() + 1000;   // OK
      #pragma omp parallel num_threads(5)
      {
         // cannot assign to 'x' here
         x = omp_get_thread_num() + 1000;   // C3899
         System::Console::WriteLine("thread {0}", omp_get_thread_num());
      }
      x = omp_get_thread_num() + 1000;   // OK
   }
};

int main() {
   R^ r = gcnew R;
   System::Console::WriteLine(r->x);
}
```
