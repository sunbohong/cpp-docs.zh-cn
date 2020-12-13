---
description: 了解更多：编译器错误 C3320
title: 编译器错误 C3320
ms.date: 11/04/2016
f1_keywords:
- C3320
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
ms.openlocfilehash: 2dde804792dec4f7a1564c680a45c78adf60eedf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337374"
---
# <a name="compiler-error-c3320"></a>编译器错误 C3320

“type”：类型不能和模块的“name”属性同名

 (UDT) 导出的用户定义类型（可以是结构、类、枚举或联合）不能与传递到 [module](../../windows/attributes/module-cpp.md) 特性的名称属性的参数具有相同的名称。

## <a name="example"></a>示例

以下示例生成 C3320：

```cpp
// C3320.cpp
#include "unknwn.h"
[module(name="xx")];

[export] struct xx {   // C3320
// Try the following line instead
// [export] struct yy {
   int i;
};
```
