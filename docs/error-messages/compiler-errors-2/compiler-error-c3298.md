---
description: 了解更多：编译器错误 C3298
title: 编译器错误 C3298
ms.date: 11/04/2016
f1_keywords:
- C3298
helpviewer_keywords:
- C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
ms.openlocfilehash: 25b0abc98d5498e59b97f83f47bc0ba12704a328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144568"
---
# <a name="compiler-error-c3298"></a>编译器错误 C3298

“constraint_1”：不能使用“constraint_2”作为约束，因为“constraint_2”具有 ref 约束，而“constraint_1”具有值约束

不能为约束指定相互排斥的特征。 例如，不能同时将泛型类型参数约束为值类型和引用类型。

有关详细信息，请参阅[泛型类型参数的约束 (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C3298。

```cpp
// C3298.cpp
// compile with: /clr /c
generic<class T, class U>
where T : ref class
where U : T, value class   // C3298
public ref struct R {};
```
