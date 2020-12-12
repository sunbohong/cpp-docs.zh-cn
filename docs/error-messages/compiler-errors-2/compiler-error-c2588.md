---
description: 了解更多：编译器错误 C2588
title: 编译器错误 C2588
ms.date: 11/04/2016
f1_keywords:
- C2588
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
ms.openlocfilehash: 7f723f826a5d4e609c0766c5287a0fffdee72d18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177570"
---
# <a name="compiler-error-c2588"></a>编译器错误 C2588

"：： ~ identifier"：非法的全局析构函数

析构函数是为类、结构或联合以外的对象定义的。 这是不允许的。

此错误可能是由范围解析的左侧缺少的类、结构或联合名称 (`::`) 运算符导致的。

下面的示例生成 C2588：

```cpp
// C2588.cpp
~F();   // C2588
```
