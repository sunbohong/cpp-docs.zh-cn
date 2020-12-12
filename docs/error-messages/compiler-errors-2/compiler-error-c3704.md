---
description: 了解更多：编译器错误 C3704
title: 编译器错误 C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: aae489b2d8657a1e62adc654d148be6cd0403af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278176"
---
# <a name="compiler-error-c3704"></a>编译器错误 C3704

"function"： vararg 方法无法激发事件

您尝试对 vararg 方法使用 [__event](../../cpp/event.md) 。 若要修复此错误，请将调用替换为 `fireEvent(int i, ...)` `fireEvent(int i)` 调用，如下面的代码示例中所示。

下面的示例生成 C3704：

```cpp
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```
