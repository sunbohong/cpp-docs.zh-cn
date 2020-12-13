---
description: 了解更多：编译器错误 C2396
title: 编译器错误 C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 654b812fbd152a6effb60e6f0919f99bf5039a1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145387"
---
# <a name="compiler-error-c2396"></a>编译器错误 C2396

"your_type：： operator'type" "： CLR 或 WinRT 用户定义的转换 functionnot 有效。 必须转换为： t ^ "，不是 ^%"，不是 ^& "，其中 T =" your_type "

Windows 运行时或托管类型中的转换函数没有至少一个类型与包含转换函数的类型相同的参数。

下面的示例生成 C2396，并演示如何修复此错误：

```cpp
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```
