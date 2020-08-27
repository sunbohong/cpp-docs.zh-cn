---
title: 编译器错误 C2702
description: 描述 Microsoft C/c + + 编译器错误 C2702。
ms.date: 08/25/2020
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: 83210f6ab261a5ae6dd7320182c3f4c3539ff4d1
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898425"
---
# <a name="compiler-error-c2702"></a>编译器错误 C2702

> `__except` 不能出现在终止块中

**`__try`** / **`__except`** 不能在块中嵌套 () 的异常处理程序 **`__finally`** 。

下面的示例生成 C2702：

```cpp
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```
