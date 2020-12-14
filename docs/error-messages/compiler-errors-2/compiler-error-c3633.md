---
description: 了解更多：编译器错误 C3633
title: 编译器错误 C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: caf89e2297bb4e9d62be76699b153f013095fa34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239254"
---
# <a name="compiler-error-c3633"></a>编译器错误 C3633

不能将 "member" 定义为托管 "type" 的成员

CLR 引用类数据成员不能为非 POD c + + 类型。  只能在 CLR 类型中实例化 POD 本机类型。  例如，POD 类型不能包含复制构造函数或赋值运算符。

## <a name="example"></a>示例

下面的示例生成 C3633。

```cpp
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
