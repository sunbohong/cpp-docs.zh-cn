---
description: 了解更多：编译器错误 C3420
title: 编译器错误 C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3c79693823255ed7335e5805c0ac17de5ddcead7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315992"
---
# <a name="compiler-error-c3420"></a>编译器错误 C3420

“finalizer”: 终结器不能为虚

终结器只能从其封闭类型进行非虚拟调用。 因此，声明虚拟终结器是错误的。

有关详细信息，请参阅 [如何：定义和使用类和结构 (c + +/cli) 中的析构函数和终结 ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)器。

## <a name="example"></a>示例

下面的示例生成 C3420。

```cpp
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```
