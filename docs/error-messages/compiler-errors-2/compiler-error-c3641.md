---
description: 了解更多：编译器错误 C3641
title: 编译器错误 C3641
ms.date: 11/04/2016
f1_keywords:
- C3641
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
ms.openlocfilehash: 391994a5207fe27cea0b33e6d03e5a1fdc30f6c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239098"
---
# <a name="compiler-error-c3641"></a>编译器错误 C3641

> "*function*"：用/clr： pure 或/clr： safe 编译的函数的调用约定 "calling_convention" 无效

## <a name="remarks"></a>备注

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

仅允许使用[/clr： pure](../../build/reference/clr-common-language-runtime-compilation.md) [__clrcall](../../cpp/clrcall.md)调用约定。

## <a name="example"></a>示例

下面的示例生成 C3641：

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```
