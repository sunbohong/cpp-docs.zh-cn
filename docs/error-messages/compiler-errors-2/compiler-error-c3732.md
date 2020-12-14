---
description: 了解更多：编译器错误 C3732
title: 编译器错误 C3732
ms.date: 11/04/2016
f1_keywords:
- C3732
helpviewer_keywords:
- C3732
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
ms.openlocfilehash: 406acf356ee0bec09eb5d9e218114256f9c58858
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245052"
---
# <a name="compiler-error-c3732"></a>编译器错误 C3732

"interface"：激发 COM 事件的自定义接口不能从 IDispatch 继承

支持 COM 事件的接口不能从继承 `IDispatch` 。 有关详细信息，请参阅 [COM 中的事件处理](../../cpp/event-handling-in-com.md)。

以下错误生成 C3732：

```cpp
// C3732.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="test")];

// to resolve this C3732, use dual instead of object
// or inherit from IUnknown
[ object ]
__interface I : IDispatch
{
};

[ event_source(com), coclass ]
struct A
{
   __event __interface I;   // C3732
};

int main()
{
}
```
