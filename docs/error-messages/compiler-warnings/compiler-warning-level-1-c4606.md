---
description: 了解详细信息：编译器警告 (等级 1) C4606
title: 编译器警告（等级 1）C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: b347be103d2a84dba2143861cb35b67f3d38fb9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341732"
---
# <a name="compiler-warning-level-1-c4606"></a>编译器警告（等级 1）C4606

\#pragma warning：忽略 "warning_number";代码分析警告与警告等级无关

对于代码分析警告， `error` `once` `default` [警告](../../preprocessor/warning.md) 杂注仅支持、和。

## <a name="example"></a>示例

下面的示例生成 C4606。

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
