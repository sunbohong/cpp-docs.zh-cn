---
description: 了解详细信息：编译器警告 (等级 1) C4186
title: 编译器警告（等级 1）C4186
ms.date: 11/04/2016
f1_keywords:
- C4186
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
ms.openlocfilehash: 08ab6c490c404d9dabef1d5222cd388b5db7a891
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266606"
---
# <a name="compiler-warning-level-1-c4186"></a>编译器警告（等级 1）C4186

\#导入特性 "attribute" 需要计数参数;掉

`#import` 特性的参数数量不正确。

## <a name="example"></a>示例

```cpp
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` 特性不采用任何参数。 **rename** 特性仅采用两个参数。
