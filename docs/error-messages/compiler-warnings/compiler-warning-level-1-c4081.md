---
description: 了解详细信息：编译器警告 (等级 1) C4081
title: 编译器警告（等级 1）C4081
ms.date: 11/04/2016
f1_keywords:
- C4081
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
ms.openlocfilehash: 01c03255361676cfbe9876c73d77a7e2c9356eda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278150"
---
# <a name="compiler-warning-level-1-c4081"></a>编译器警告（等级 1）C4081

需要“token1”；找到“token2”

在此上下文中，编译器需要另一个标记。

## <a name="example"></a>示例

```cpp
// C4081.cpp
// compile with: /W1 /LD
#pragma optimize) "l", on )   // C4081
```
