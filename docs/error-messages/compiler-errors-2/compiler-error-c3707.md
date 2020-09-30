---
title: 编译器错误 C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: a09bf080c72e154a37cec5cdb75e714c12dd7150
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507985"
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
