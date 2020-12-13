---
description: 了解更多：编译器警告 C4986
title: 编译器警告 C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: 5d068ee376c6ae6ce1fb3563d66c7bda871da0ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336040"
---
# <a name="compiler-warning-c4986"></a>编译器警告 C4986

“function”: 异常规范与前面的声明不匹配

当一个声明中存在异常规范而其他声明中没有时，则可能产生此警告。

默认情况下，C4986 处于关闭状态。 有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

## <a name="examples"></a>示例

下面的示例生成 C4986。

```cpp
class X { };
void f1() throw (X*);
// ...
void f1()
{
    // ...
}
```

以下示例将消除此警告。

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```
