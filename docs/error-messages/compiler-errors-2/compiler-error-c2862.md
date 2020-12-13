---
description: 了解更多：编译器错误 C2862
title: 编译器错误 C2862
ms.date: 11/04/2016
f1_keywords:
- C2862
helpviewer_keywords:
- C2862
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
ms.openlocfilehash: 80b2a3d597c3289024d025bac35f5e0aeab44c58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151107"
---
# <a name="compiler-error-c2862"></a>编译器错误 C2862

"interface"：接口只能有公共成员

仅可从其他成员函数访问受保护的私有成员。 此类成员不能在接口中使用，因为它可能不会为其任何成员提供实现。

下面的示例将生成 C2862：

```cpp
// C2862.cpp
// compile with: /c
#include <unknwn.h>

[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]
__interface IMyInterface {
   HRESULT mf1(void);   // OK
protected:
   HRESULT mf2(int *b);   // C2862
private:
   HRESULT mf3(int *c);   // C2862
};
```
