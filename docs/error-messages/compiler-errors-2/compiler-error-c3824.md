---
description: 了解更多：编译器错误 C3824
title: 编译器错误 C3824
ms.date: 11/04/2016
f1_keywords:
- C3824
helpviewer_keywords:
- C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
ms.openlocfilehash: 5560ee8c845c57ae14de11b503ebc724dbcbb0dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249355"
---
# <a name="compiler-error-c3824"></a>编译器错误 C3824

"member"：此类型不能出现在此上下文中 (函数参数、返回类型或静态成员) 

固定指针不能是函数参数、返回类型或已声明 **`static`** 。

## <a name="example"></a>示例

下面的示例生成 C3824：

```cpp
// C3824a.cpp
// compile with: /clr /c
void func() {
   static pin_ptr<int> a; // C3824
   pin_ptr<int> b; // OK
}
```
