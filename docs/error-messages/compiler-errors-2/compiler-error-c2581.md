---
description: 了解更多：编译器错误 C2581
title: 编译器错误 C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: 9de6c48c2ade71af238cc62a0f92e642e1262d3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282115"
---
# <a name="compiler-error-c2581"></a>编译器错误 C2581

"type"：静态 "operator =" 函数是非法的

赋值 (`=`) 运算符被错误地声明为 **`static`** 。 赋值运算符不能为 **`static`** 。 有关详细信息，请参阅 [用户定义的运算符 (c + +/cli) ](../../dotnet/user-defined-operators-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C2581。

```cpp
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```
