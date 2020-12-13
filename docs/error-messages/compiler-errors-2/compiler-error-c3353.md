---
description: 了解更多：编译器错误 C3353
title: 编译器错误 C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: 50ff7a6b104f3e16ce17f1398da49a146c0d41a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335036"
---
# <a name="compiler-error-c3353"></a>编译器错误 C3353

“delegate”: 委托只能从全局函数或者托管或 WinRT 类型的成员函数中创建

用 [委托](../../extensions/delegate-cpp-component-extensions.md) 关键字声明的委托只能在全局范围内声明。

以下示例生成 C3353：

```cpp
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```
