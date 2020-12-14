---
description: 了解更多：编译器错误 C3418
title: 编译器错误 C3418
ms.date: 11/04/2016
f1_keywords:
- C3418
helpviewer_keywords:
- C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
ms.openlocfilehash: 38082b7fe9ffa0ebcc7b4857e77395664a9f0c42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316227"
---
# <a name="compiler-error-c3418"></a>编译器错误 C3418

不支持访问说明符“specifier”

不正确地指定了 CLR 访问说明符。  有关详细信息，请参阅 [如何：定义和使用类和结构 (c + +/cli) ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)中的类型可见性和成员可见性。

## <a name="example"></a>示例

下面的示例生成 C3418。

```cpp
// C3418.cpp
// compile with: /clr /c
ref struct m {
internal public:   // C3418
   void test(){}
};

ref struct n {
internal:   // OK
   void test(){}
};
```
