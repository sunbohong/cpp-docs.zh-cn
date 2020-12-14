---
description: 了解更多：编译器错误 C2775
title: 编译器错误 C2775
ms.date: 11/04/2016
f1_keywords:
- C2775
helpviewer_keywords:
- C2775
ms.assetid: 9c488508-ade0-48f1-b94f-d538d15f807a
ms.openlocfilehash: f7a24cfa3b868d08c86a08deaa13ec6067f4a9eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298157"
---
# <a name="compiler-error-c2775"></a>编译器错误 C2775

"identifier"：没有 "get" 方法与该属性关联

使用 [属性](../../cpp/property-cpp.md) 扩展特性声明的数据成员未 `get` 指定函数，但表达式尝试检索其值。

下面的示例生成 C2775：

```cpp
// C2775.cpp
struct A {
   __declspec(property(put=PutProp2, get=GetProp2)) int prop2;
   int GetProp2(){return 0;}
   void PutProp2(int){}

   __declspec(property(put=PutProp)) int prop;
   int PutProp(void){}

};

int main() {
   A* pa = new A;
   int x;
   x = pa->prop;   // C2775
   x = pa->prop2;
}
```
