---
description: 了解详细信息：严重错误 C1018
title: 错误 C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 68b81406916ef358a73112c9f6f8b2370c627e54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316409"
---
# <a name="fatal-error-c1018"></a>错误 C1018

意外的 #elif

`#elif` 指令出现在 `#if`、 `#ifdef`或 `#ifndef` 构造外部。 仅在这些构造之一中使用 `#elif` 。

下面的示例生成 C1018：

```cpp
// C1018.cpp
#elif      // C1018
#endif

int main() {}
```

可能的解决方法：

```cpp
// C1018b.cpp
#if 1
#elif
#endif

int main() {}
```
