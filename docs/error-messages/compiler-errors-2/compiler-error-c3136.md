---
description: 了解更多：编译器错误 C3136
title: 编译器错误 C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: 4203eaa1f41603075bbb8162b7156783c8f2680a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239371"
---
# <a name="compiler-error-c3136"></a>编译器错误 C3136

"interface"： COM 接口只能从另一个 COM 接口继承，"interface" 不是 COM 接口

应用了 [接口特性](../../windows/attributes/interface-attributes.md) 的接口继承自非 COM 接口的接口。 COM 接口最终继承自 `IUnknown` 。 任何前面带有 interface 特性的接口都是一个 COM 接口。

下面的示例生成 C3136：

```cpp
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```
