---
description: 了解更多：编译器错误 C3080
title: 编译器错误 C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 746e5527118c617983e96d02a584a0aa4508c64c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320149"
---
# <a name="compiler-error-c3080"></a>编译器错误 C3080

“finalizer_function”：终结器不能具有存储类说明符

有关详细信息，请参阅 [如何：定义和使用类和结构 (c + +/cli) 中的析构函数和终结 ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)器。

## <a name="example"></a>示例

下面的示例生成 C3080。

```cpp
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```
