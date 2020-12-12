---
description: 详细了解：编译器警告 (等级 3) C4792
title: 编译器警告（等级 3）C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: 37dc805477e3150eedaffe7eb5d900b7903b1d48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332129"
---
# <a name="compiler-warning-level-3-c4792"></a>编译器警告（等级 3）C4792

函数“function”使用 sysimport 声明并从本机代码引用；需要链接导入库

从非托管函数调用通过 DllImport 导入到程序中的本机函数。 因此，你必须链接到该 DLL 的导入库。

无法在代码中解决该警告，也无法通过改变编译方式来解决。 请使用 [警告](../../preprocessor/warning.md) 杂注禁用此警告。

以下示例生成 C4792：

```cpp
// C4792.cpp
// compile with: /clr /W3
// C4792 expected
using namespace System::Runtime::InteropServices;
[DllImport("msvcrt")]
extern "C" int __cdecl puts(const char *);
int main() {}

// Uncomment the following line to resolve.
// #pragma warning(disable : 4792)
#pragma unmanaged
void func(void){
   puts("test");
}
```
