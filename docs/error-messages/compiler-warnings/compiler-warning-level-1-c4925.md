---
description: 了解详细信息：编译器警告 (等级 1) C4925
title: 编译器警告（等级 1）C4925
ms.date: 11/04/2016
f1_keywords:
- C4925
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
ms.openlocfilehash: 0fefea9580631439c9e442bb737f39b5c236b229
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301940"
---
# <a name="compiler-warning-level-1-c4925"></a>编译器警告（等级 1）C4925

“method”：不能从脚本调用调度接口方法

脚本语言不能创建 VT_BYREF“in”参数，只能创建 VT_BYREF“out”参数。

解决此警告的另一种方法是不令该参数（在定义和实现中）为指针类型。

下面的示例生成 C4925：

```cpp
// C4925.cpp
// compile with: /LD /W1
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[ module(name="Test")];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IDisp {
   [id(9)] void f([in] int*);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]
struct CDisp : IDisp {   // C4925
   void f(int*) {}
};
```
