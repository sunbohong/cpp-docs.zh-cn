---
description: 了解更多：编译器错误 C2732
title: 编译器错误 C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 1ca97fbf46685af1df37b8caf82a03effc1ec6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123209"
---
# <a name="compiler-error-c2732"></a>编译器错误 C2732

链接规范与“function”的早期规范冲突

该函数已经使用其他链接说明符声明。

具有不同链接说明符的包含文件可能会导致此错误。

若要修复此错误，请更改 **`extern`** 语句，使链接一致。 特别是，不要对 `extern "C"` 块中的 `#include` 指令换行。

## <a name="example"></a>示例

下面的示例生成 C2732：

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
