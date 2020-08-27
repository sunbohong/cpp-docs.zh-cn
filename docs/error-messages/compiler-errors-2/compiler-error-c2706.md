---
title: 编译器错误 C2706
description: 描述 Microsoft C/c + + 编译器错误 C2706。
ms.date: 08/25/2020
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: 11e1e878f82ad59bb712155747696c0d6c6a239e
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898740"
---
# <a name="compiler-error-c2706"></a>编译器错误 C2706

> `__except`没有匹配的 `__try` (在块中缺少 "}" 的非法 `__try` ) 

编译器找不到块的右大括号 **`__try`** 。

下面的示例生成 C2706：

```cpp
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```
