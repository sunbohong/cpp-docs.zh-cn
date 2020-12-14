---
description: 了解更多：编译器错误 C2279
title: 编译器错误 C2279
ms.date: 11/04/2016
f1_keywords:
- C2279
helpviewer_keywords:
- C2279
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
ms.openlocfilehash: e0f8822c77bd243bc2ec6002027d8eadb2aaf8a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228971"
---
# <a name="compiler-error-c2279"></a>编译器错误 C2279

异常规范不能出现在 typedef 声明中

在 **/za** 下，typedef 声明中不允许出现 [异常规范](../../cpp/exception-specifications-throw-cpp.md) 。

下面的示例生成 C2279：

```cpp
// C2279.cpp
// compile with: /Za /c
typedef int (*xy)() throw(...);   // C2279
typedef int (*xyz)();   // OK
```
