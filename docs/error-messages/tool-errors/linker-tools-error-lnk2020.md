---
description: 了解详细信息：链接器工具错误 LNK2020
title: 链接器工具错误 LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 61e999b2f451359e3a806bc2da5f2beb431e6fab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275849"
---
# <a name="linker-tools-error-lnk2020"></a>链接器工具错误 LNK2020

未解析的标记 "token"

类似于未定义的外部错误，只不过引用是通过元数据的。 在元数据中，必须定义所有函数和数据。

若要解决问题，请执行以下操作：

- 定义缺少的函数或数据，或

- 包含已在其中定义缺少的函数或数据的对象文件或库。

## <a name="examples"></a>示例

下面的示例生成 LNK2020。

```cpp
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

如果创建托管模板类型的变量，但不同时实例化该类型，则也会发生 LNK2020。

下面的示例生成 LNK2020。

```cpp
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```
