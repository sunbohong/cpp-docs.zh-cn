---
description: 了解更多：编译器错误 C3912
title: 编译器错误 C3912
ms.date: 11/04/2016
f1_keywords:
- C3912
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
ms.openlocfilehash: 5c7828fa055aff08ea57759bdf3ee9b9677cc0f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144061"
---
# <a name="compiler-error-c3912"></a>编译器错误 C3912

"event"：事件类型必须是委托类型

已声明事件，但它的类型不正确。

有关详细信息，请参阅 [事件](../../extensions/event-cpp-component-extensions.md)。

下面的示例生成 C3912：

```cpp
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```
