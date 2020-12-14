---
description: 了解更多：编译器警告 C4950
title: 编译器警告 C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: e1bb05501fcac6c836bfd4aa89f72807b625c292
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314875"
---
# <a name="compiler-warning-c4950"></a>编译器警告 C4950

“type_or_member”：标记为过时

使用特性将成员或类型标记为过时 <xref:System.ObsoleteAttribute> 。

始终发出 C4950 错误。 您可以通过使用 [warning](../../preprocessor/warning.md) pragma 指令或 [/wd](../../build/reference/compiler-option-warning-level.md) 编译器选项来关闭此警告。

## <a name="example"></a>示例

下面的示例生成 C4950：

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```
