---
description: 了解更多：编译器错误 C3626
title: 编译器错误 C3626
ms.date: 11/04/2016
f1_keywords:
- C3626
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
ms.openlocfilehash: 8db976a5f072db618ac4270df3bd1d8edf0ab15c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144412"
---
# <a name="compiler-error-c3626"></a>编译器错误 C3626

"关键字"： "__event" 关键字只能用于作为指向委托的指针的 COM 接口、成员函数和数据成员

关键字未正确使用。

下面的示例生成 C3626：

```cpp
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```
