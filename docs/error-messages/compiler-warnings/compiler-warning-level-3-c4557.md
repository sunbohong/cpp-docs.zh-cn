---
description: 详细了解：编译器警告 (等级 3) C4557
title: 编译器警告（等级 3）C4557
ms.date: 11/04/2016
f1_keywords:
- C4557
helpviewer_keywords:
- C4557
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
ms.openlocfilehash: 606c1cdb36d79b13ad914912fb570c82e38eed2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257779"
---
# <a name="compiler-warning-level-3-c4557"></a>编译器警告（等级 3）C4557

“__assume”包含效果“effect”

已修改传递到 [__assume](../../intrinsics/assume.md) statement2 的值。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4557：

```cpp
// C4557.cpp
// compile with: /W3
#pragma warning(default : 4557)
int main()
{
   int i;
   __assume(i++);   // C4557
}
```
