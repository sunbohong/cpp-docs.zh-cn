---
description: 了解更多：编译器错误 C3384
title: 编译器错误 C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: 79d5aabf185702c3d85485744b14e714a32aa76b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285573"
---
# <a name="compiler-error-c3384"></a>编译器错误 C3384

“type_parameter”: 值约束与 ref 约束互相排斥

不能将泛型类型约束为 **`value class`** 和 **`ref class`** 。

有关详细信息，请参阅有关 [c + +/cli)  (泛型类型参数的约束 ](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 。

## <a name="example"></a>示例

下面的示例生成 C3384。

```cpp
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```
