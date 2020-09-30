---
title: 编译器错误 C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 14f0cedc5448005a29d74f05ae3e68e74eb5cf1c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508307"
---
# <a name="compiler-error-c3171"></a>编译器错误 C3171

"module"：在项目中不能指定不同的模块特性

在编译中的两个文件中找到具有不同参数列表的[模块](../../windows/attributes/module-cpp.md)属性。 `module`每个编译只能指定一个唯一属性。

`module`在多个源代码文件中可以指定相同的特性。

例如，如果 `module` 找到以下属性：

```cpp
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

然后，

```cpp
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

编译器将生成 C3171 (注意) 的不同版本值。
