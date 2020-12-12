---
description: 了解更多：编译器错误 C3364
title: 编译器错误 C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: e500b984489de1dfc2cd68d91ac5cb457d3887f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150847"
---
# <a name="compiler-error-c3364"></a>编译器错误 C3364

"delegate"：委托构造函数：参数必须是指向托管类或全局函数的成员函数的指针

委托构造函数的第二个参数采用成员函数的地址或任何类的静态成员函数的地址。 两者都被视为简单地址。

下面的示例生成 C3364：

```cpp
// C3364_2.cpp
// compile with: /clr

delegate int D( int, int );

ref class C {
public:
   int mf( int, int ) {
      return 1;
   }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364

   // try the following line instead
   // System::Delegate^ pD = gcnew D(pC, &C::mf);
}
```
