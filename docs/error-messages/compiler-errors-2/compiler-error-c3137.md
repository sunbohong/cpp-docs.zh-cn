---
description: 了解更多：编译器错误 C3137
title: 编译器错误 C3137
ms.date: 11/04/2016
f1_keywords:
- C3137
helpviewer_keywords:
- C3137
ms.assetid: 70bb1313-2e87-43ed-a0d8-33fa6ff475e4
ms.openlocfilehash: 7c4954e66eb019eaa11e8e17b760926e5396c0ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239319"
---
# <a name="compiler-error-c3137"></a>编译器错误 C3137

"property"：属性不能初始化

例如，在构造函数的初始化列表中不能初始化属性。

下面的示例生成 C3137：

```cpp
// C3137.cpp
// compile with: /clr /c
ref class CMyClass {
public:
   property int Size {
      int get() {
         return 0;
      }
      void set( int i ) {}
   }

   CMyClass() : Size( 1 ) {   // C3137
      // to resolve this C3137, remove the initializer from the
      // ctor declaration and perform the assignment as follows
      // Size = 1;
   }
};
```
