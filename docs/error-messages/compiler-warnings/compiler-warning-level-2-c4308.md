---
description: 详细了解：编译器警告 (等级 2) C4308
title: 编译器警告（等级 2）C4308
ms.date: 11/04/2016
f1_keywords:
- C4308
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
ms.openlocfilehash: 180372bef17180b74431ea3c317417f15a6a231d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339186"
---
# <a name="compiler-warning-level-2-c4308"></a>编译器警告（等级 2）C4308

负整型常量转换为无符号类型

表达式将负整数常量转换为无符号类型。 表达式的结果可能毫无意义。

## <a name="example"></a>示例

```cpp
// C4308.cpp
// compile with: /W2
unsigned int u = (-5 + 3U);   // C4308

int main()
{
}
```
