---
title: 编译器错误 C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: ca0eab35f6e60d81a324156905619ceb7ace8830
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508286"
---
# <a name="compiler-error-c3172"></a>编译器错误 C3172

"module_name"：不能在项目中指定不同的 idl_module 特性

[idl_module](../../windows/attributes/idl-module.md)在 `dllname` `version` 编译中的两个文件中找到了具有相同名称但具有不同或参数的 idl_module 属性。 `idl_module`每个编译只能指定一个唯一属性。

`idl_module`在多个源代码文件中可以指定相同的特性。

例如，如果 `idl_module` 找到以下属性：

```cpp
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

然后，

```cpp
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

编译器将生成 C3172 (注意) 的不同版本值。
