---
description: 了解更多：编译器错误 C2341
title: 编译器错误 C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 47869b6534664358fa80a3ace89fc44fdceefb08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234782"
---
# <a name="compiler-error-c2341"></a>编译器错误 C2341

"节名称"：必须使用 #pragma data_seg、code_seg 或部分定义段，然后才能使用

[Allocate](../../cpp/allocate.md)语句引用了尚未由[code_seg](../../preprocessor/code-seg.md)、 [data_seg](../../preprocessor/data-seg.md)或[节](../../preprocessor/section.md)杂注定义的段。

下面的示例生成 C2341：

```cpp
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

可能的解决方法：

```cpp
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
