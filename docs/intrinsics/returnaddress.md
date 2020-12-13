---
description: 了解详细信息： _ReturnAddress
title: _ReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _ReturnAddress
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
ms.openlocfilehash: abb6b879c466372fce0ecbeb7371101e3a3ef82b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143736"
---
# <a name="_returnaddress"></a>_ReturnAddress

**Microsoft 专用**

`_ReturnAddress`内部函数提供调用函数中的指令的地址，该指令将在控件返回到调用方之后执行。

生成以下程序并在调试器中单步执行。 单步执行此程序时，请记下从返回的地址 `_ReturnAddress` 。 然后，在从使用的函数返回后立即 `_ReturnAddress` 打开 [操作方法：使用 "反汇编" 窗口](/visualstudio/debugger/how-to-use-the-disassembly-window) ，并注意下一个要执行的指令的地址与从返回的地址匹配 `_ReturnAddress` 。

内联等优化可能会影响返回地址。 例如，如果下面的示例程序用 [/Ob1](../build/reference/ob-inline-function-expansion.md)编译，则 `inline_func` 会内联到调用函数中 `main` 。 因此，对和的 `_ReturnAddress` 调用 `inline_func` `main` 将生成相同的值。

当 `_ReturnAddress` 在使用 [/clr](../build/reference/clr-common-language-runtime-compilation.md)编译的程序中使用时，包含该调用的函数 `_ReturnAddress` 将编译为本机函数。 当编译为对包含的函数的托管调用的函数时 `_ReturnAddress` ， `_ReturnAddress` 可能不会按预期方式运行。

## <a name="requirements"></a>要求

**头文件** \<intrin.h>

## <a name="example"></a>示例

```cpp
// compiler_intrinsics__ReturnAddress.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_ReturnAddress)

__declspec(noinline)
void noinline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

__forceinline
void inline_func(void)
{
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());
}

int main(void)
{
   noinline_func();
   inline_func();
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());

   return 0;
}
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)\
[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[关键字](../cpp/keywords-cpp.md)
