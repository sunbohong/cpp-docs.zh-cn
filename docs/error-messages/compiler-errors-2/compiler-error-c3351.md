---
description: 了解更多：编译器错误 C3351
title: 编译器错误 C3351
ms.date: 11/04/2016
f1_keywords:
- C3351
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
ms.openlocfilehash: 324d927f0a54ea5750cbea45827152a66546cba7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144530"
---
# <a name="compiler-error-c3351"></a>编译器错误 C3351

“object”：委托构造函数：第二个参数必须为静态成员函数或全局函数的地址

编译器需要声明的函数的地址 **`static`** 。

以下示例生成 C3351：

```cpp
// C3351a.cpp
// compile with: /clr
delegate int D(int, int);

ref class C {
public:
   int mf(int, int) {
      return 1;
   }

   static int mf2(int, int) {
      return 1;
   }
};

int main() {
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351
   System::Delegate ^pD2 = gcnew D(&C::mf2);
}
```
