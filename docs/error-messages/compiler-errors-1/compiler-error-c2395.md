---
description: 了解更多：编译器错误 C2395
title: 编译器错误 C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 86b6123646ca91945a861e9b9822076877421ac8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145465"
---
# <a name="compiler-error-c2395"></a>编译器错误 C2395

“your_type::operator'op'”：CLR 或 WinRT 运算符无效。 至少一个参数必须是以下类型： "t"、"t%"、"& t"、"t ^"、"t ^%"、"t ^&"，其中 T = "your_type"

Windows 运行时或托管的类型中的一个运算符没有至少一个类型与运算符返回值的类型相同的参数。

下面的示例生成 C2395，并演示如何修复此错误：

```cpp
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```
