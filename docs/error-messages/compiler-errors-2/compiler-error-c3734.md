---
title: 编译器错误 C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 0d49eae823eb64f97e7276d432e161b3de21d725
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510069"
---
# <a name="compiler-error-c3734"></a>编译器错误 C3734

“class”: 托管或 WinRT 类不能是组件类

[Coclass](../../windows/attributes/coclass.md)特性不能与托管或 WinRT 类一起使用。

下面的示例生成 C3734，并演示如何修复此错误：

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
