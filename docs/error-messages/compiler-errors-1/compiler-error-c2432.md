---
description: 了解更多：编译器错误 C2432
title: 编译器错误 C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: 392108e0fd16952bc8bcf43682dc163c664171ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190011"
---
# <a name="compiler-error-c2432"></a>编译器错误 C2432

"identifier" 中对16位数据的非法引用

16位寄存器用作索引或基寄存器。 编译器不支持引用16位数据。 编译32位代码时，16位寄存器不能用作索引或基寄存器。

下面的示例生成 C2432：

```cpp
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```
