---
description: 了解更多：编译器错误 C3417
title: 编译器错误 C3417
ms.date: 11/04/2016
f1_keywords:
- C3417
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
ms.openlocfilehash: d51985f619c436a1dfd6af06b97c72c3d06c7967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321892"
---
# <a name="compiler-error-c3417"></a>编译器错误 C3417

"member"：值类型不能包含用户定义的特殊成员函数

值类型不能包含诸如默认实例构造函数、析构函数或复制构造函数之类的函数。

下面的示例生成 C3517：

```cpp
// C3417.cpp
// compile with: /clr /c
value class VC {
   VC(){}   // C3417

   // OK
   static VC(){}
   VC(int i){}
};
```
