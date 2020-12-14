---
description: 了解更多：编译器错误 C2386
title: 编译器错误 C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: 65dca1cf052cab1292f6f594a316536a5097a032
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204090"
---
# <a name="compiler-error-c2386"></a>编译器错误 C2386

“symbol”：当前范围内已存在具有该名称的符号

你尝试创建命名空间别名，但所选名称已存在。

以下示例生成 C2386：

```cpp
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```
