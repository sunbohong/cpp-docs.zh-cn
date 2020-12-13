---
description: 详细了解：编译器警告 (级别 4) C4918
title: 编译器警告（等级 4）C4918
ms.date: 11/04/2016
f1_keywords:
- C4918
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
ms.openlocfilehash: 268fbff753ff5ed0cc2d63df6ba8422cdf073662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330446"
---
# <a name="compiler-warning-level-4-c4918"></a>编译器警告（等级 4）C4918

“character”: 杂注优化列表中的无效字符

在 [optimize](../../preprocessor/optimize.md) 杂注语句的优化列表中发现未知字符。

例如，以下语句生成 C4918：

```cpp
// C4918.cpp
// compile with: /W4
#pragma optimize("X", on) // C4918 expected
int main()
{
}
```
