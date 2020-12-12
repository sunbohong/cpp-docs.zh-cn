---
description: 了解详细信息：严重错误 C1017
title: 错误 C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: a36a5cb11b10ca3ecca00d0379595060918d6a45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262381"
---
# <a name="fatal-error-c1017"></a>错误 C1017

无效的整数常量表达式

指令中的表达式 `#if` 不存在或者其计算结果不是常数。

使用定义的常量的 `#define` 值必须为整数常量（如果在 `#if` 、或指令中使用） `#elif` `#else` 。

下面的示例生成 C1017：

```cpp
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

可能的解决方法：

```cpp
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

由于 `CONSTANT_NAME` 计算结果为字符串而不是整数，因此 `#if` 指令生成错误 C1017。

在其他情况下，预处理器将未定义的常数计算为零。 这可能会导致意外的结果，如以下示例中所示。 `YES` 未定义，因此它的计算结果为零。 表达式的 `#if` `CONSTANT_NAME` 计算结果为 false，并且预处理器移除了要使用的代码 `YES` 。 `NO` 还未定义 (零) ，因此 `#elif` `CONSTANT_NAME==NO` 计算结果为 true (`0 == 0`) ，导致预处理器将代码保留在语句的一部分中，这与 `#elif` 预期行为完全相反。

```cpp
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

若要确切了解编译器如何处理预处理器指令，请使用 [/p](../../build/reference/p-preprocess-to-a-file.md)、 [/e](../../build/reference/e-preprocess-to-stdout.md)或 [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)。
