---
description: 了解详细信息：编译器警告 (等级 1) C4683
title: 编译器警告（等级 1）C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: e7f2c76e7f15bb7342e60b2aa390cf0bd1a8ce05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285235"
---
# <a name="compiler-warning-level-1-c4683"></a>编译器警告（等级 1）C4683

> "*function*"：事件源有 "输出" 参数;挂钩多个事件处理程序时的注意事项

## <a name="remarks"></a>备注

如果有多个事件接收器正在侦听 COM 事件源，则可能会忽略 out 参数的值。

请注意，在下列情况下会发生内存泄漏：

1. 如果方法具有内部分配的 out 参数（例如 BSTR *），则为。

2. 如果事件有多个处理程序 (是多路广播事件) 。

泄漏的原因是，out 参数将由多个处理程序设置，但仅由上一个处理程序返回到调用站点。

## <a name="example"></a>示例

下面的示例生成 C4683，并演示如何修复此问题：

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```
