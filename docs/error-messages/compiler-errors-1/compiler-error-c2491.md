---
description: 了解更多：编译器错误 C2491
title: 编译器错误 C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 4fd12e30672d7045aa4a7506b35b845e8cd018c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283690"
---
# <a name="compiler-error-c2491"></a>编译器错误 C2491

"identifier"：不允许使用 dllimport 函数的定义

可以将数据、静态数据成员和函数声明为 `dllimport`，但不能定义为 `dllimport`。

若要解决此问题，请从函数定义中 `__declspec(dllimport)` 删除说明符。

以下示例生成 C2491：

```cpp
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```
