---
description: 了解更多：编译器错误 C2535
title: 编译器错误 C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: 149ddabcde7364513379701c55d4801fd403206b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258078"
---
# <a name="compiler-error-c2535"></a>编译器错误 C2535

"identifier"：已定义或声明成员函数

此错误的原因可能是在多个定义或重载函数声明中使用了相同的形参表。

如果由于 Dispose 函数而获得 C2535，请参阅 [析构函数和终结](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 器以了解详细信息。

下面的示例生成 C2535：

```cpp
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```
