---
description: 了解更多：编译器错误 C2810
title: 编译器错误 C2810
ms.date: 11/04/2016
f1_keywords:
- C2810
helpviewer_keywords:
- C2810
ms.assetid: f63e8f24-d7f6-42ac-904f-72ff49592ba6
ms.openlocfilehash: 609a1ccd89619ddb66b42a81cf9a769480670508
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320582"
---
# <a name="compiler-error-c2810"></a>编译器错误 C2810

"interface"：接口只能从另一个接口继承

[接口](../../cpp/interface.md)只能从另一个接口继承，并且不能从类或结构继承。

下面的示例生成 C2810：

```cpp
// C2810.cpp
#include <unknwn.h>
class CBase1 {
public:
  HRESULT mf1();
  int  m_i;
};

[object, uuid="40719E20-EF37-11D1-978D-0000F805D73B"]
__interface IDerived : public CBase1 {  // C2810
// try the following line instead
// __interface IDerived {
   HRESULT mf2(void *a);
};

struct CBase2 {
   HRESULT mf1(int a, char *b);
   HRESULT mf2();
};
```
