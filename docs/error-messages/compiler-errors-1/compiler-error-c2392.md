---
description: 了解更多：编译器错误 C2392
title: 编译器错误 C2392
ms.date: 11/04/2016
f1_keywords:
- C2392
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
ms.openlocfilehash: 0a367ed1416b28bb27fc5d79d4a474de219e48e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337559"
---
# <a name="compiler-error-c2392"></a>编译器错误 C2392

"method1"：托管或 WinRTtypes 中不支持协变返回类型，否则 "method2" 将被重写

Windows 运行时成员函数或使用 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md) 选项进行编译时，不允许协变返回类型。

## <a name="example"></a>示例

下面的示例生成了 C2392，并演示了如何修复此错误。

```cpp
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```
