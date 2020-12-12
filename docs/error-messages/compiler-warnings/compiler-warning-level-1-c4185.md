---
description: 了解详细信息：编译器警告 (等级 1) C4185
title: 编译器警告（等级 1）C4185
ms.date: 11/04/2016
f1_keywords:
- C4185
helpviewer_keywords:
- C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
ms.openlocfilehash: 7fb2e11ef0a287190424d2d2f5287fc0b2ed1575
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266645"
---
# <a name="compiler-warning-level-1-c4185"></a>编译器警告（等级 1）C4185

忽略未知的 #import 特性“attribute”

该特性不是有效的 `#import`特性。 它将被忽略。

## <a name="example"></a>示例

```cpp
// C4185.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_such_attribute   // C4185
```
