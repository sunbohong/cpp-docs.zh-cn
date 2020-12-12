---
description: 了解更多：编译器错误 C3366
title: 编译器错误 C3366
ms.date: 11/04/2016
f1_keywords:
- C3366
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
ms.openlocfilehash: 922fa882efcaead4df87bbfc104394e12b797955
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150834"
---
# <a name="compiler-error-c3366"></a>编译器错误 C3366

"variable"：托管或 WinRTtypes 的静态数据成员必须在类定义中定义

尝试在 WinRT 或 .NET 类/接口定义外部引用该类或接口的静态成员。

编译器需要知道类的完整定义（以在一次传递后发出元数据）并要求在类中初始化静态数据成员。

例如，下面的示例生成 C3366，并演示如何修复此错误：

```cpp
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
