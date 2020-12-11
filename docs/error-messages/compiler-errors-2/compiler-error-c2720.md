---
description: 了解更多：编译器错误 C2720
title: 编译器错误 C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: 187142af02289374235725340a206f35b6a42493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155652"
---
# <a name="compiler-error-c2720"></a>编译器错误 C2720

> "*identifier*"：成员上的 "*说明符*" 存储类说明符非法

存储类无法用于声明外部的类成员。 若要修复此错误，请从类声明外部的成员定义中删除不需要的 [存储类](../../cpp/storage-classes-cpp.md) 说明符。

## <a name="example"></a>示例

下例生成了 C2720，并介绍了如何修复此错误：

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```
