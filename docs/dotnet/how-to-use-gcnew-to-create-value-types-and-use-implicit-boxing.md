---
description: 了解详细信息：如何：使用 gcnew 创建值类型和使用隐式装箱
title: 如何：使用 gcnew 创建值类型并使用隐式装箱
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: e58b50be4399cef6a842ce0b02e951617f143e5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210889"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>如何：使用 gcnew 创建值类型并使用隐式装箱

对值类型使用 [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) 会创建一个装箱的值类型，然后可以将其放置在托管的垃圾回收堆中。

## <a name="example"></a>示例

```cpp
// vcmcppv2_explicit_boxing4.cpp
// compile with: /clr
public value class V {
public:
   int m_i;
   V(int i) : m_i(i) {}
};

public ref struct TC {
   void do_test(V^ v) {
      if (v != nullptr)
         ;
      else
         ;
   }
};

int main() {
   V^ v = gcnew V(42);
   TC^ tc = gcnew TC;
   tc->do_test(v);
}
```

## <a name="see-also"></a>请参阅

[装箱](../extensions/boxing-cpp-component-extensions.md)
