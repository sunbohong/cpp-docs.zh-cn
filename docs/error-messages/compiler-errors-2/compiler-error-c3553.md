---
description: 了解更多：编译器错误 C3553
title: 编译器错误 C3553
ms.date: 11/04/2016
f1_keywords:
- C3553
helpviewer_keywords:
- C3553
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
ms.openlocfilehash: 43e322b78bac05f6e301501a86ce7fbd2f27d285
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223212"
---
# <a name="compiler-error-c3553"></a>编译器错误 C3553

> decltype 应为表达式而不是类型

`decltype()` 关键字要求使用表达式作为参数，而非类型的名称。 例如，以下代码片段中的最后一个语句生成错误 C3553。

```cpp
int x = 0;
decltype(x+1);
decltype(int); // C3553
```
