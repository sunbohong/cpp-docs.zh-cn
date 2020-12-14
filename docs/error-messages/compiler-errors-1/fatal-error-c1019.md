---
description: 了解详细信息：严重错误 C1019
title: 错误 C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: d11a4300b29e497fef2f148d07963997586781ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316383"
---
# <a name="fatal-error-c1019"></a>错误 C1019

意外的 #else

`#else` 指令出现在 `#if`、 `#ifdef`或 `#ifndef` 构造外部。 仅在这些构造之一中使用 `#else` 。

下面的示例生成 C1019：

```cpp
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

可能的解决方法：

```cpp
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```
