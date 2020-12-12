---
description: 了解更多：编译器错误 C2731
title: 编译器错误 C2731
ms.date: 11/04/2016
f1_keywords:
- C2731
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
ms.openlocfilehash: baae65ff1d09bafe37251b7593dc0d0c91c89f1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123300"
---
# <a name="compiler-error-c2731"></a>编译器错误 C2731

"identifier"：无法重载函数

函数 `main` 、、 `WinMain` `DllMain` 和 `LibMain` 无法重载。

下面的示例生成 C2731：

```cpp
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```
