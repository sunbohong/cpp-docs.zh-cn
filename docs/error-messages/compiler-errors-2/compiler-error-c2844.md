---
description: 了解更多：编译器错误 C2844
title: 编译器错误 C2844
ms.date: 11/04/2016
f1_keywords:
- C2844
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
ms.openlocfilehash: 030d8526e7bfd85e7bcca1c115f1b5ce5d45c3aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260273"
---
# <a name="compiler-error-c2844"></a>编译器错误 C2844

"member"：不能是接口 "interface" 的成员

[接口类](../../extensions/interface-class-cpp-component-extensions.md)不能包含数据成员，除非它也是一个属性。

在接口中不允许使用属性或成员函数之外的任何内容。 此外，不允许使用构造函数、析构函数和运算符。

下面的示例生成 C2844：

```cpp
// C2844a.cpp
// compile with: /clr /c
public interface class IFace {
   int i;   // C2844
   // try the following line instead
   // property int Size;
};
```
