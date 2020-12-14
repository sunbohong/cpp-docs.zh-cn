---
description: 了解详细信息：严重错误 C1022
title: 错误 C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: cd608aded29b4f3ebf329586ebc03ce2e325c970
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249758"
---
# <a name="fatal-error-c1022"></a>错误 C1022

应输入 #endif

`#if`、 `#ifdef`或 `#ifndef` 指令没有匹配的 `#endif` 指令。 确保每个 `#if`、 `#ifdef`或 `#ifndef` 都有一个相匹配的 `#endif`。

以下示例生成 C1022：

```cpp
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

可能的解决方法：

```cpp
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```
