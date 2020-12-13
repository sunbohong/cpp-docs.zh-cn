---
description: 了解详细信息： __debugbreak
title: __debugbreak
ms.date: 09/02/2019
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 83a670d9fa9c1f6b41c1c405c59af71c7aa0c8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337105"
---
# <a name="__debugbreak"></a>__debugbreak

**Microsoft 专用**

将在代码中引起断点，并在其中提示用户运行调试程序。

## <a name="syntax"></a>语法

```C
void __debugbreak();
```

## <a name="requirements"></a>要求

|Intrinsic|体系结构|标头|
|---------------|------------------|------------|
|`__debugbreak`|x86、x64、ARM、ARM64|\<intrin.h>|

## <a name="remarks"></a>备注

`__debugbreak`编译器内部函数（类似于[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)）是导致断点的可移植 Win32 方法。

> [!NOTE]
> 使用 **/clr** 进行编译时，包含的函数 `__debugbreak` 将编译为 MSIL。 `asm int 3` 可将函数编译为本机函数。 有关详细信息，请参阅 [__asm](../assembler/inline/asm.md)。

例如：

```C
main() {
   __debugbreak();
}
```

类似于：

```C
main() {
   __asm {
      int 3
   }
}
```

在 x86 计算机上。

在 ARM64 上，将 `__debugbreak` 内部函数编译到指令中 `brk #0xF000` 。

此例程仅可用作内部函数。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[关键字](../cpp/keywords-cpp.md)
