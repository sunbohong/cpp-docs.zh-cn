---
description: 了解更多：编译器错误 C3368
title: 编译器错误 C3368
ms.date: 11/04/2016
f1_keywords:
- C3368
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
ms.openlocfilehash: 1b7fadb59bc0944b5092a235dfa0cb90c2233daa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150808"
---
# <a name="compiler-error-c3368"></a>编译器错误 C3368

“function declaration”：IDL 的调用约定无效

你只能在 .idl 文件中使用 [__stdcall](../../cpp/stdcall.md) 或 [__cdecl](../../cpp/cdecl.md) 调用约定。

以下示例生成 C3368：

```cpp
// C3368.cpp
// processor: x86
[idl_module(name="Name", dllname="Some.dll")];

[idl_module(name="Name")]
int __fastcall f1();   // C3368
```
