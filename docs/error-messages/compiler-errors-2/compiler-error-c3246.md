---
description: 了解更多：编译器错误 C3246
title: 编译器错误 C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: 5a74b642abe2e184e8e505ec1000433357de2522
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307179"
---
# <a name="compiler-error-c3246"></a>编译器错误 C3246

“class”: 无法从“type”继承，因为它已声明为“sealed”

标记为 [sealed](../../extensions/sealed-cpp-component-extensions.md) 的类不能为任何其他类的基类。

以下示例生成 C3246：

```cpp
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
