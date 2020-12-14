---
description: 了解更多：编译器错误 C2776
title: 编译器错误 C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 75e0121c61fd55aa89e6ffcc6e1ed00137fcaaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298131"
---
# <a name="compiler-error-c2776"></a>编译器错误 C2776

每个属性只能指定一个 "get" 方法

只能 `get` 在 [属性](../../cpp/property-cpp.md) 扩展属性中指定一个函数。 当指定多个函数时，会出现此错误 `get` 。

下面的示例生成 C2776：

```cpp
// C2776.cpp
struct A {
   __declspec(property(get=GetProp,get=GetPropToo))
   // try the following line instead
   // __declspec(property(get=GetProp))
      int prop;   // C2776
   int GetProp(void);
   int GetPropToo(void);
};
```
