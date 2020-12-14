---
description: 了解更多：编译器错误 C3213
title: 编译器错误 C3213
ms.date: 11/04/2016
f1_keywords:
- C3213
helpviewer_keywords:
- C3213
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
ms.openlocfilehash: 5ae16ffd94c6d300956bb2723ccbe8c16b0d6b3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291761"
---
# <a name="compiler-error-c3213"></a>编译器错误 C3213

基类“base_type”的可访问性比“derived_type”低

程序集中可见的类型必须使用公开可见的基类。

以下示例生成 C3213：

```cpp
// C3213.cpp
// compile with: /clr
private ref struct privateG {
public:
   int i;
};

public ref struct publicG {
public:
   int i;
};

public ref struct V : public privateG {   // C3213
public:
   int j;
};

public ref struct W: public publicG {   // OK
public:
   int j;
};
```
