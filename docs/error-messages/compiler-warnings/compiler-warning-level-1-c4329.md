---
description: 了解详细信息：编译器警告 (等级 1) C4329
title: 编译器警告（等级 1）C4329
ms.date: 11/04/2016
f1_keywords:
- C4329
helpviewer_keywords:
- C4329
ms.assetid: 4316f51a-2c56-4b3f-831e-65d24b83b65c
ms.openlocfilehash: 210395694c581f7d37e1612bbdcb60e29f5e0bba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311560"
---
# <a name="compiler-warning-level-1-c4329"></a>编译器警告（等级 1）C4329

__declspec (对齐 ( # A2 # A3 在枚举上被忽略

不允许对使用 [__declspec](../../cpp/declspec.md)修饰符的 [align](../../cpp/align-cpp.md)关键字 **`enum`** 。 下面的示例生成 C4329：

```cpp
// C4329.cpp
// compile with: /W1 /LD
enum __declspec(align(256)) TestEnum {   // C4329
   TESTVAL1,
   TESTVAL2,
   TESTVAL3
};
__declspec(align(256)) enum TestEnum1;
```
