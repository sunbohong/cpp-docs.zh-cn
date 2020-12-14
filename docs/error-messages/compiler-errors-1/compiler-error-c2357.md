---
description: 了解更多：编译器错误 C2357
title: 编译器错误 C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: a58317fc4706d6385d3753a434c8e4fd80dc79b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276733"
---
# <a name="compiler-error-c2357"></a>编译器错误 C2357

"identifier"：必须是 "type" 类型的函数

你的代码声明的函数版本 `atexit` 与编译器内部声明的版本不匹配。 声明 `atexit` 如下：

```
int __cdecl atexit(void (__cdecl *)());
```

有关详细信息，请参阅 [init_seg](../../preprocessor/init-seg.md)。

下面的示例生成 C2357：

```cpp
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```
