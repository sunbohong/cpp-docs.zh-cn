---
description: 了解更多：编译器错误 C3910
title: 编译器错误 C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: 802aac0d27e230920a906b96afc78100296c75de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144139"
---
# <a name="compiler-error-c3910"></a>编译器错误 C3910

"event"：必须定义成员 "method"

定义了一个事件，但它不包含指定的、必需的访问器方法。

有关详细信息，请参阅 [事件](../../extensions/event-cpp-component-extensions.md)。

下面的示例生成 C3910：

```cpp
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```
