---
description: 了解详细信息：编译器警告 (等级 1) C4618
title: 编译器警告（等级 1）C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: 824a55dab68fe45a94cacb1924bed46b87b7c0eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208679"
---
# <a name="compiler-warning-level-1-c4618"></a>编译器警告（等级 1）C4618

pragma 参数包括空字符串;已忽略杂注

将空字符串作为参数提供给了 **#pragma**。

在没有参数的情况下处理杂注。

下面的示例生成 C4618：

```cpp
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```
