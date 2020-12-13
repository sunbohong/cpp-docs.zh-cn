---
description: 了解更多：编译器错误 C2861
title: 编译器错误 C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: 82a4ed7d4b157bc141e9d437fa0f1d575759b48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151120"
---
# <a name="compiler-error-c2861"></a>编译器错误 C2861

"function name"：不能定义接口成员函数

编译器遇到了 interface 关键字或将结构推导为接口，但找到了成员函数定义。  接口不能包含成员函数的定义。

## <a name="example"></a>示例

下面的示例生成 C2861：

```cpp
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```
