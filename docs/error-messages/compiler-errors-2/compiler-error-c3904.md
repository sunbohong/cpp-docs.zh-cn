---
description: 了解更多：编译器错误 C3904
title: 编译器错误 C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 0b1564e609586318d23b4204242f0cb39034c4fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144178"
---
# <a name="compiler-error-c3904"></a>编译器错误 C3904

"property_accessor"：必须指定 number 参数 (s) 

`get`对照属性维度检查和方法中的参数数量 `set` 。

- 此方法的参数数目 `get` 必须等于属性的维度数，或为零（对于非索引属性）。

- 此方法的参数数目 `set` 必须大于属性的维度数。

有关详细信息，请参阅 [property](../../extensions/property-cpp-component-extensions.md)。

## <a name="examples"></a>示例

下面的示例生成 C3904。

```cpp
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

下面的示例生成 C3904。

```cpp
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```
