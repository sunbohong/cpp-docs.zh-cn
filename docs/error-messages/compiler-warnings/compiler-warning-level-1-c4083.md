---
description: 了解详细信息：编译器警告 (等级 1) C4083
title: 编译器警告 (等级 1) C4083
ms.date: 11/04/2016
f1_keywords:
- C4083
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
ms.openlocfilehash: 2913e4a55b7c777ae4c910631b8fb10120dd3463
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272326"
---
# <a name="compiler-warning-level-1-c4083"></a>编译器警告 (等级 1) C4083

应为 "token";找到标识符 "identifier"

标识符出现在 **#pragma** 语句中错误的位置。

## <a name="example"></a>示例

```cpp
// C4083.cpp
// compile with: /W1 /LD
#pragma warning disable:4083    // C4083
#pragma warning(disable:4083)   //correct
```

检查 [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 指令的语法。
