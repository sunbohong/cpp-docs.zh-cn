---
description: 了解详细信息：严重错误 C1020
title: 错误 C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 444da85bddf65533eb5ae37278085664efeae7ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316357"
---
# <a name="fatal-error-c1020"></a>错误 C1020

意外的 #endif

`#endif` 指令有没有匹配的 `#if`、 `#ifdef`或 `#ifndef` 指令。 确保每个 `#endif` 具有匹配的指令。

下面的示例生成 C1020：

```cpp
// C1020.cpp
#endif     // C1020
```

可能的解决方法：

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
