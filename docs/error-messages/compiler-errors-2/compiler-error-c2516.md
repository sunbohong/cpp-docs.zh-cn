---
description: 了解更多：编译器错误 C2516
title: 编译器错误 C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: 1561a6917d26a9cc4c71a8970e7a75512c1a1b61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339295"
---
# <a name="compiler-error-c2516"></a>编译器错误 C2516

"name"：不是合法基类

类派生自语句定义的类型名称 **`typedef`** 。

下面的示例生成 C2516：

```cpp
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```
