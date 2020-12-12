---
description: 了解更多：编译器错误 C3701
title: 编译器错误 C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: 8ebc8ac41091770a59876fb829d86997d7f5709c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228685"
---
# <a name="compiler-error-c3701"></a>编译器错误 C3701

"function"： event_source 没有事件

尝试在没有事件方法的类上使用 [event_source](../../windows/attributes/event-source.md) 。 若要修复此错误，请向类添加一个或多个事件。

下面的示例生成 C3701：

```cpp
// C3701.cpp
[ event_source(native) ]
class CEventSrc {
public:
   // uncomment the following line to resolve this C3701
   // __event void fireEvent(int i);
};   // C3701

int main() {
}
```
