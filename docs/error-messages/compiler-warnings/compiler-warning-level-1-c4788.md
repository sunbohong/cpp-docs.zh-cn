---
description: 了解详细信息：编译器警告 (等级 1) C4788
title: 编译器警告（等级 1）C4788
ms.date: 11/04/2016
f1_keywords:
- C4788
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
ms.openlocfilehash: 2aa87fd8a09b9f308e7fbb51fc4f05792210b0c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234600"
---
# <a name="compiler-warning-level-1-c4788"></a>编译器警告（等级 1）C4788

"identifier"：标识符被截断为 "number" 个字符

编译器会限制函数名称允许的最大长度。 当编译器生成 EH/SEH 代码的 funclets 时，它会通过在函数名称前面加一些文本（例如 "__catch"、" \_ _unwind" 或另一个字符串）来形成 funclet 名称。

生成的 funclet 名称可能太长，编译器将截断该名称并生成 C4788。

若要解决此警告，请缩短原始函数名称。 如果函数是 c + + 模板函数或方法，请对名称的部分使用 typedef。 例如：

```cpp
C1<x, y, z<T>>::C2<a,b,c>::f
```

可以替换为：

```cpp
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;
new_class::f
```

仅在 x64 编译器中出现此警告。
