---
description: 了解更多：编译器错误 C3116
title: 编译器错误 C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: ea11d851c4348725c48e408ffdd0ed6de4393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115932"
---
# <a name="compiler-error-c3116"></a>编译器错误 C3116

"存储说明符"：接口方法的存储类无效

你使用 **`typedef`** **`register`** 了、或 **`static`** 作为接口方法的存储类。 这些存储类在接口成员上不允许。

下面的示例生成 C3116：

```cpp
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```
