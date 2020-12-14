---
description: 了解更多：编译器错误 C3755
title: 编译器错误 C3755
ms.date: 11/04/2016
f1_keywords:
- C3755
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
ms.openlocfilehash: 24d6af223b6a15cbf1740bf67144250007c2091d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253580"
---
# <a name="compiler-error-c3755"></a>编译器错误 C3755

"delegate"：不能定义委托

可以声明但不能定义 [ (c + + 组件扩展) 的委托 ](../../extensions/delegate-cpp-component-extensions.md) 。

## <a name="examples"></a>示例

下面的示例生成 C3755。

```cpp
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

如果尝试创建委托模板，也可能会发生 C3755。 下面的示例生成 C3755。

```cpp
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```
