---
description: 了解更多：编译器错误 C2161
title: 编译器错误 C2161
ms.date: 11/04/2016
f1_keywords:
- C2161
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
ms.openlocfilehash: bafbcceee5f09f6d0d29d3a501dc94929d69b9eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177973"
---
# <a name="compiler-error-c2161"></a>编译器错误 C2161

“##”不能在宏定义的结尾处出现

以标记粘贴运算符结尾 (##) 的宏定义。

以下示例生成 C2161：

```cpp
// C2161.cpp
// compile with: /c
#define mac(a,b) a   // OK
#define mac(a,b) a##   // C2161
```
