---
description: 了解更多：编译器错误 C3915
title: 编译器错误 C3915
ms.date: 11/04/2016
f1_keywords:
- C3915
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
ms.openlocfilehash: c1b2e6fb1dd77c315d29bbd704960963766f8931
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143944"
---
# <a name="compiler-error-c3915"></a>编译器错误 C3915

"type" 没有 (类索引器的默认索引属性) 

类型没有默认的索引属性。

有关详细信息，请参阅 [property](../../extensions/property-cpp-component-extensions.md)。

## <a name="examples"></a>示例

下面的示例生成 C3915。

```cpp
// C3915.cpp
// compile with: /clr
ref class X {
public:
// uncomment property to resolve this C3915
//   property int default[]
//   {
//      int get(int i)
//      {
//         return 863;
//      }
//   }
};

int main() {
   X^ x = new X;
   System::Console::WriteLine(x[1]);   // C3915
}
```

如果尝试在定义默认索引器的同一编译单位中使用默认索引器，也可能会发生 C3915 <xref:System.Reflection.DefaultMemberAttribute> 。

下面的示例生成 C3915。

```cpp
// C3915_b.cpp
// compile with: /clr
using namespace System;

[Reflection::DefaultMember("XXX")]
ref struct A {
   property Double XXX[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

ref struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

int main() {
   A ^ mya = gcnew A();
   Console::WriteLine("{0}", mya[3]);   // C3915

   B ^ myb = gcnew B();
   Console::WriteLine("{0}", myb[3]);   // OK
}
```
