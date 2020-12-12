---
description: 了解更多：编译器错误 C3768
title: 编译器错误 C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: 3203fe74fb1da91f24312f76ca11ac49711da8f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291709"
---
# <a name="compiler-error-c3768"></a>编译器错误 C3768

> 无法在纯托管代码中获取虚拟 vararg 函数的地址

## <a name="remarks"></a>备注

**/Clr： pure** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

使用 **/clr： pure** 进行编译时，无法获取虚函数的地址 `vararg` 。

## <a name="example"></a>示例

下面的示例生成 C3768：

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```
