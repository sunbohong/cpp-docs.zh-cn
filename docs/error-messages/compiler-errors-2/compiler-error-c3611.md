---
description: 了解更多：编译器错误 C3611
title: 编译器错误 C3611
ms.date: 11/04/2016
f1_keywords:
- C3611
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
ms.openlocfilehash: 9c18e8e757e3962af1f2e0fbcc0d33384f3b6329
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262290"
---
# <a name="compiler-error-c3611"></a>编译器错误 C3611

"function"：密封函数不能具有纯说明符

未正确声明密封函数。  有关详细信息，请参阅 [sealed](../../extensions/sealed-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3611。

```cpp
// C3611.cpp
// compile with: /clr /c

ref struct V {
   virtual void Test() sealed = 0;   // C3611
   virtual void Test2() sealed;   // OK
   virtual void Test3() = 0;   // OK
};
```
