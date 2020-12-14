---
description: 了解更多：编译器错误 C3374
title: 编译器错误 C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: b3ec1a18433c41f8c1e1a4b704b6ab03dae7572d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245169"
---
# <a name="compiler-error-c3374"></a>编译器错误 C3374

不能采用“函数”的地址，除非创建委托实例

在上下文中而不是委托实例的创建中采用函数的地址。

以下示例生成 C3374：

```cpp
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>请参阅

[如何：定义和使用委托 (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)
