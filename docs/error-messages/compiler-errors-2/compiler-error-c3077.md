---
description: 了解更多：编译器错误 C3077
title: 编译器错误 C3077
ms.date: 11/04/2016
f1_keywords:
- C3077
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
ms.openlocfilehash: a8e6a15f38427727939fbaabb0bfcf4d9e315d77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320162"
---
# <a name="compiler-error-c3077"></a>编译器错误 C3077

“finalizer”：终结器只能是引用类型的成员

不能在本机类型或值类型中声明终结器。

有关详细信息，请参阅 [如何：定义和使用类和结构 (c + +/cli) 中的析构函数和终结 ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)器。

## <a name="example"></a>示例

下面的示例生成 C3077。

```cpp
// C3077.cpp
// compile with: /clr /c
value struct vs {
   !vs(){}   // C3077
};

ref struct rs {
protected:
   !rs(){}   // OK
};
```
