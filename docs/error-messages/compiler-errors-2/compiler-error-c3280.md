---
description: 了解更多：编译器错误 C3280
title: 编译器错误 C3280
ms.date: 11/04/2016
f1_keywords:
- C3280
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
ms.openlocfilehash: f85731b20e98088fdfd8e894a942ce8d16b553bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194171"
---
# <a name="compiler-error-c3280"></a>编译器错误 C3280

“class”: 无法将托管类型的成员函数编译成非托管函数

托管的类成员函数不能编译为非托管函数。

以下示例生成 C3280：

```cpp
// C3280_2.cpp
// compile with: /clr
ref struct A {
   void func();
};

#pragma managed(push,off)

void A::func()   // C3280
{
}

#pragma managed(pop)
```
