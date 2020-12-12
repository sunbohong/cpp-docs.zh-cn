---
description: 了解更多：编译器错误 C3352
title: 编译器错误 C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: 66d6921c86c6b7a30026880f01ab2a5dada11a65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150938"
---
# <a name="compiler-error-c3352"></a>编译器错误 C3352

"function"：指定的函数与委托类型 "type" 不匹配

和委托的参数列表 `function` 不匹配。

有关详细信息，请参阅 [) 的委托 (c + + 组件扩展 ](../../extensions/delegate-cpp-component-extensions.md)。

下面的示例生成 C3352：

```cpp
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```
