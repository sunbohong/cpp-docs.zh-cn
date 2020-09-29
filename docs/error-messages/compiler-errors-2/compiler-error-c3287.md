---
title: 编译器错误 C3287
description: 描述 Microsoft c + + 编译器错误 C3287。
ms.date: 09/25/2020
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: 4067355ef1bc1992d0f8519656bcd1063179aef4
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414315"
---
# <a name="compiler-error-c3287"></a>编译器错误 C3287

> 类型 "*type*" (GetEnumerator 的返回类型) 必须具有合适的公共 MoveNext 成员函数和公共的 Current 属性

## <a name="remarks"></a>备注

用户定义的集合类必须包含对 `MoveNext` 和 `Current`的定义。

有关详细信息，请参阅 [中的](../../dotnet/for-each-in.md)。

## <a name="example"></a>示例

以下示例生成 C3287。

```cpp
// C3287.cpp
// compile with: /clr
using namespace System;

ref struct R {
   bool MoveNext() {
      return true;
   }
   property Object^ Current {
      Object^ get() {
         Object ^ o = gcnew Object;
         return o;
      }
   }
};

ref struct R2 {
   R ^GetEnumerator() {
      R^ r = gcnew R;
      return r;
   }
};

ref struct T {};

ref struct T2 {
   T ^GetEnumerator() {
      T^ t = gcnew T;
      return t;
   }
};

int main() {
   for each (int i in gcnew T2) {}   // C3287
   for each (int i in gcnew R2) {}   // OK
}
```
