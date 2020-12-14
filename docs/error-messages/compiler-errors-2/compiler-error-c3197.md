---
description: 了解更多：编译器错误 C3197
title: 编译器错误 C3197
ms.date: 11/04/2016
f1_keywords:
- C3197
helpviewer_keywords:
- C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
ms.openlocfilehash: f03792a2dd5120ed2b4a05b2110186d5c985e502
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203752"
---
# <a name="compiler-error-c3197"></a>编译器错误 C3197

"关键字"：只能在定义中使用

关键字用于声明中，但仅在定义中有效。

下面的示例生成 C3197：

```cpp
// C3197.cpp
// compile with: /clr /c
ref struct R abstract;   // C3197
ref struct R abstract {};   // OK

public ref class MyObject;   // C3197
ref class MyObject;   // OK
public ref class MyObject {};   // OK
```
