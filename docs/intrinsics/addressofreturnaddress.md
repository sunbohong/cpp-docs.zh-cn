---
description: 了解详细信息： _AddressOfReturnAddress
title: _AddressOfReturnAddress
ms.date: 09/02/2019
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: 1a79ccbe7ddc2865d8225a62cd0d294f0bc66b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331924"
---
# <a name="_addressofreturnaddress"></a>_AddressOfReturnAddress

**Microsoft 专用**

提供保存当前函数的返回地址的内存位置的地址。 此地址不能用于访问其他内存位置 (例如，函数的参数) 。

## <a name="syntax"></a>语法

```C
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>要求

|Intrinsic|体系结构|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86、x64、ARM、ARM64|

**头文件** \<intrin.h>

## <a name="remarks"></a>备注

当 `_AddressOfReturnAddress` 在使用 [/clr](../build/reference/clr-common-language-runtime-compilation.md)编译的程序中使用时，包含该调用的函数将 `_AddressOfReturnAddress` 编译为本机函数。 当编译为对包含的函数的托管调用的函数时 `_AddressOfReturnAddress` ， `_AddressOfReturnAddress` 可能不会按预期方式运行。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```cpp
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[关键字](../cpp/keywords-cpp.md)
