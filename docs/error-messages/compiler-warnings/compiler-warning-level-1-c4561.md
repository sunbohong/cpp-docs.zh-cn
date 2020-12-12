---
description: 了解详细信息：编译器警告 (等级 1) C4561
title: 编译器警告（等级 1）C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: fc94879039f72bba0734240bc26d152965d6b650
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337285"
---
# <a name="compiler-warning-level-1-c4561"></a>编译器警告（等级 1）C4561

"__fastcall" 与 "/clr" 选项不兼容：转换为 " \_ _stdcall"

[__Fastcall](../../cpp/fastcall.md)函数调用约定不能与[/clr](../../build/reference/clr-common-language-runtime-compilation.md)编译器选项一起使用。 编译器将忽略对的调用 **`__fastcall`** 。 若要修复此警告，请删除对的调用 **`__fastcall`** 或不带 **/clr** 编译的。

下面的示例生成 C4561：

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```
