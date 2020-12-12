---
description: 了解更多：编译器错误 C3131
title: 编译器错误 C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 3fde5045f2c14efdac96f902e12dcea1f5118505
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177401"
---
# <a name="compiler-error-c3131"></a>编译器错误 C3131

项目必须具有 "module" 特性和 "name" 属性

[Module](../../windows/attributes/module-cpp.md)特性必须具有 name 参数。

下面的示例生成 C3131：

```cpp
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```
