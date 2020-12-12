---
description: 了解更多：编译器错误 C2734
title: 编译器错误 C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c867ef8456be35d0e566056aedc4de43d16c8f14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123170"
---
# <a name="compiler-error-c2734"></a>编译器错误 C2734

"identifier"：如果不是 extern，则必须初始化常量对象

已声明标识符， **`const`** 但未对其进行初始化或 **`extern`** 。

下面的示例生成 C2734：

```cpp
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```
