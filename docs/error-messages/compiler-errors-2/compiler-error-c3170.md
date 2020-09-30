---
title: 编译器错误 C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: c4eb4a2551312791d05c8badb66af0070e74b630
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508326"
---
# <a name="compiler-error-c3170"></a>编译器错误 C3170

项目中不能有不同的模块标识符

在编译中的两个文件中找到具有不同名称的[模块](../../windows/attributes/module-cpp.md)属性。 `module`每个编译只能指定一个唯一属性。

`module`在多个源代码文件中可以指定相同的特性。

例如，如果找到以下模块属性：

```cpp
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

然后，

```cpp
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

编译器将生成 C3170 (注意不同的名称) 。
