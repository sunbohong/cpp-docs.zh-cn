---
description: 了解更多：编译器错误 C3638
title: 编译器错误 C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 1d1cc59cd8065a5b0e661292b717ba885c6febeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239189"
---
# <a name="compiler-error-c3638"></a>编译器错误 C3638

"operator"：不能重新定义标准装箱和取消装箱转换运算符

编译器为每个托管类定义一个转换运算符，以支持隐式装箱。 不能重新定义此运算符。

有关详细信息，请参阅 [隐式装箱](../../extensions/boxing-cpp-component-extensions.md)。

下面的示例生成 C3638：

```cpp
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```
