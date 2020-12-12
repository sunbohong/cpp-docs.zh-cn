---
description: 了解详细信息：编译器警告 (等级 1) C4810
title: 编译器警告（等级 1）C4810
ms.date: 11/04/2016
f1_keywords:
- C4810
helpviewer_keywords:
- C4810
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
ms.openlocfilehash: 4cebcf6b4cabc2539d5fcf25363f573a704ae577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328091"
---
# <a name="compiler-warning-level-1-c4810"></a>编译器警告（等级 1）C4810

杂注 pack(show) 的值 == n

当你使用 **pack** 杂注的“显示” [](../../preprocessor/pack.md) 选项时，将发出此警告。 *n* 是当前的 pack 值。

例如，下面的代码演示 C4810 警告如何处理 pack 杂注：

```cpp
// C4810.cpp
// compile with: /W1 /LD
// C4810 expected
#pragma pack(show)
#pragma pack(4)
#pragma pack(show)
```
