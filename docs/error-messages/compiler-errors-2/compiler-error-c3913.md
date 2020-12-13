---
description: 了解更多：编译器错误 C3913
title: 编译器错误 C3913
ms.date: 11/04/2016
f1_keywords:
- C3913
helpviewer_keywords:
- C3913
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
ms.openlocfilehash: 92db9f0c198d07453968c1d01a63ee33e2998594
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144074"
---
# <a name="compiler-error-c3913"></a>编译器错误 C3913

必须将默认属性编入索引

未正确定义默认属性。

有关详细信息，请参阅 [property](../../extensions/property-cpp-component-extensions.md)。

下面的示例生成 C3913：

```cpp
// C3913.cpp
// compile with: /clr /c
ref struct X {
   property int default {   // C3913
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```
