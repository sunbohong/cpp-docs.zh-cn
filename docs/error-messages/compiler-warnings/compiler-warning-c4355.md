---
description: 了解更多：编译器警告 C4355
title: 编译器警告 C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: fd4d38aae7a3728370c89cb2298438dbc0ba616c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180768"
---
# <a name="compiler-warning-c4355"></a>编译器警告 C4355

“this”: 用于基成员初始值设定项列表

**`this`** 指针仅在非静态成员函数中有效。 它不能用于基类的初始化表达式列表中。

基类构造函数和类成员构造函数在 **`this`** 构造函数之前调用。 实际上，已将指向未构造对象的指针传递到另一个构造函数。 如果这些其他构造函数访问任何成员或调用此上的成员函数，则结果将不确定。 在 **`this`** 所有构造完成之前，不应使用指针。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4355：

```cpp
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```
