---
description: 了解详细信息：编译器警告 (等级 1) C4939
title: 编译器警告（等级 1）C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: e31d59321ee5c2f6f154ebcaac4b74054db2604e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328031"
---
# <a name="compiler-warning-level-1-c4939"></a>编译器警告（等级 1）C4939

\#pragma vtordisp 已弃用，并将在将来的版本中删除 Visual C++

将从 Visual C++ 将来的版本中删除 [vtordisp](../../preprocessor/vtordisp.md) 杂注。

## <a name="example"></a>示例

下面的示例生成 C4939。

```cpp
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```
