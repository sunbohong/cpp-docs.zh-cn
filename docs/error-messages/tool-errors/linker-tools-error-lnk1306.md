---
description: 了解详细信息：链接器工具错误 LNK1306
title: 链接器工具错误 LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: aa6386da7c836eea8365d8a4ffde0bbd80d0fa81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193651"
---
# <a name="linker-tools-error-lnk1306"></a>链接器工具错误 LNK1306

> 无法管理 DLL 入口点函数;编译为本机

`DllMain` 不能编译为 MSIL;它必须编译为本机。

若要解决此问题，

- 编译包含没有 **/clr** 的入口点的文件。

- 将入口点置于某个 `#pragma unmanaged` 部分。

有关详细信息，请参阅：

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed、unmanaged](../../preprocessor/managed-unmanaged.md)

- [混合程序集的初始化](../../dotnet/initialization-of-mixed-assemblies.md)

- [DLL 和 Visual C++ 运行时库行为](../../build/run-time-library-behavior.md)

## <a name="example"></a>示例

下面的示例生成 LNK1306。

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

若要解决此问题，请不要使用/clr 选项来编译此文件，也不要使用 `#pragma` 指令将入口点定义放置在非托管节中，如以下示例中所示：

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```
