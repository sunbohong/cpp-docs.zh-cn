---
description: 了解详细信息：严重错误 C1191
title: 错误 C1191
ms.date: 11/04/2016
f1_keywords:
- C1191
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
ms.openlocfilehash: ef7f9ec6554daf0d83f3e597877509025512a6d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123573"
---
# <a name="fatal-error-c1191"></a>错误 C1191

"dll" 只能在全局范围内导入

将 mscorlib.dll 导入到使用/clr 编程的程序的指令不能出现在命名空间或函数中，但必须出现在全局范围内。

下面的示例生成 C1191：

```cpp
// C1191.cpp
// compile with: /clr
namespace sample {
   #using <mscorlib.dll>   // C1191 not at global scope
}
```

可能的解决方法：

```cpp
// C1191b.cpp
// compile with: /clr /c
#using <mscorlib.dll>
namespace sample {}
```
