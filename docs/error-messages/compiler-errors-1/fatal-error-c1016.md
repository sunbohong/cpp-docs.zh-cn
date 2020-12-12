---
description: 了解详细信息：严重错误 C1016
title: 错误 C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: e0f9a887c42c7006a31124446021ebee54225984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262407"
---
# <a name="fatal-error-c1016"></a>错误 C1016

\#ifdef 需要标识符 # ifndef 应输入标识符

条件编译指令（[#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) 或 `#ifndef`）没有要计算的标识符。 若要解决此错误，请指定标识符。

下面的示例生成 C1016：

```cpp
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

可能的解决方法：

```cpp
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```
