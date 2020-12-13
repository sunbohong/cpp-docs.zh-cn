---
description: 了解更多：编译器错误 C2612
title: 编译器错误 C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: 34ff229f493ccbab8c41e011caaabea818d79de9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338676"
---
# <a name="compiler-error-c2612"></a>编译器错误 C2612

基/成员初始值设定项列表中的尾随 "char" 非法

初始值设定项列表中的最后一个基或成员后会出现一个字符。

下面的示例生成 C2612：

```cpp
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```
