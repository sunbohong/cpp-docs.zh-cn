---
description: 了解更多：编译器错误 C2428
title: 编译器错误 C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: a91819591251e1c291ef8a3291525c0493af20ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190141"
---
# <a name="compiler-error-c2428"></a>编译器错误 C2428

"operation"：在 "bool" 类型的操作数上不允许

不能将减量运算符应用于类型的对象 **`bool`** 。

下面的示例生成 C2428：

```cpp
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```
