---
description: 了解更多：编译器错误 C3181
title: 编译器错误 C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: b9b9c6e8c6271abbea2d97adf92f33c35eb2028b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174125"
---
# <a name="compiler-error-c3181"></a>编译器错误 C3181

"type"：运算符的操作数无效

向 [typeid](../../extensions/typeid-cpp-component-extensions.md) 运算符传递了一个无效参数。 参数必须是托管类型。

请注意，编译器对映射到公共语言运行时中的类型的本机类型使用别名。

下面的示例生成 C3181：

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
