---
description: 了解详细信息：编译器警告 (等级 1) C4085
title: 编译器警告（等级 1）C4085
ms.date: 11/04/2016
f1_keywords:
- C4085
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
ms.openlocfilehash: 81a752e1497f0b65e99de53b14879220b58678ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155431"
---
# <a name="compiler-warning-level-1-c4085"></a>编译器警告（等级 1）C4085

杂注参数应为“on”或者“off”

杂注需要 **on** 或 **off** 参数。 将忽略杂注。

下面的示例生成 C4085：

```cpp
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```
