---
description: 了解更多：编译器错误 C2345
title: 编译器错误 C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: 021c792a93fa27712087908ab30e1ddec84d08fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298404"
---
# <a name="compiler-error-c2345"></a>编译器错误 C2345

align(value)：非法的对齐值

向 [align](../../cpp/align-cpp.md) 关键字传递了允许范围之外的值。

下面的代码生成 C2345

```cpp
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```
