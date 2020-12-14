---
description: 了解更多：编译器错误 C3707
title: 编译器错误 C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 77a1193eae9b9d0158065978438b5af1d2176d12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241841"
---
# <a name="compiler-error-c3707"></a>编译器错误 C3707

"function"：调度接口方法必须有 dispid

如果使用 `dispinterface` 方法，则必须将其分配给 `dispid` 。 若要修复此错误，请将分配 `dispid` 给 `dispinterface` 方法，例如，通过在 `id` 下面的示例中的方法上取消注释属性。 有关详细信息，请参阅属性 [调度接口](../../windows/attributes/dispinterface.md) 和 [id](../../windows/attributes/id.md)。

下面的示例生成 C3707：

```cpp
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```
