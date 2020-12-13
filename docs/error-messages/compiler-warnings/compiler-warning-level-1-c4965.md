---
description: 了解详细信息：编译器警告 (等级 1) C4965
title: 编译器警告（等级 1）C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: a3e20fa7007daac6f9a1c6f4761e222d5ab1e86c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344271"
---
# <a name="compiler-warning-level-1-c4965"></a>编译器警告（等级 1）C4965

整数0的隐式框;使用 nullptr 或显式强制转换

Visual C++ 功能隐式装箱值类型。 使用 Managed Extensions for C++ 导致空赋值的指令现在变为对装箱的 int 的赋值。

有关更多信息，请参见 [装箱](../../extensions/boxing-cpp-component-extensions.md)中定义的接口的私有 C++ 特定实现。

## <a name="example"></a>示例

下面的示例生成 C4965。

```cpp
// C4965.cpp
// compile with: /clr /W1
int main() {
   System::Object ^o = 0;   // C4965

   // the previous line is the same as the following line
   // using Managed Extensions for C++
   // System::Object *o = __box(0);

   // OK
   System::Object ^o2 = nullptr;
   System::Object ^o3 = safe_cast<System::Object^>(0);
}
```
