---
description: 了解更多：编译器错误 C2724
title: 编译器错误 C2724
ms.date: 11/04/2016
f1_keywords:
- C2724
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
ms.openlocfilehash: c11ac7521528446504a74e0f6f22c1ea24735626
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155496"
---
# <a name="compiler-error-c2724"></a>编译器错误 C2724

"identifier"： "static" 不应在文件范围内定义的成员函数上使用

应通过外部链接声明静态成员函数。

下面的示例生成 C2724：

```cpp
// C2724.cpp
class C {
   static void func();
};

static void C::func(){};   // C2724
// try the following line instead
// void C::func(){};
```
