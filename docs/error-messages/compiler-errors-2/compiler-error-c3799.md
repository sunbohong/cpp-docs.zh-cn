---
description: 了解更多：编译器错误 C3799
title: 编译器错误 C3799
ms.date: 11/04/2016
f1_keywords:
- C3799
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
ms.openlocfilehash: 31ada62b9bc347ce4d4889eca72d8d8e9c2987e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291618"
---
# <a name="compiler-error-c3799"></a>编译器错误 C3799

索引属性不能具有空参数列表

未正确声明索引属性。 有关详细信息，请参阅 [如何：使用 c + +/cli 中的属性](../../dotnet/how-to-use-properties-in-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C3799，并演示如何修复此问题。

```cpp
// C3799.cpp
// compile with: /clr /c
ref struct C {
   property int default[] {   // C3799
   // try the following line instead
   // property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};
```
