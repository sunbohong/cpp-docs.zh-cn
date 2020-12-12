---
description: 了解更多：编译器错误 C2422
title: 编译器错误 C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 4fb35b7613e523c750d6c3f15a8071117edba46a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120238"
---
# <a name="compiler-error-c2422"></a>编译器错误 C2422

"操作数" 中的非法段重写

内联程序集代码错误地将段重写运算符用于操作数)  (冒号。  可能的原因包括：

- 运算符前面的寄存器不是段寄存器。

- 运算符前面的寄存器不是操作数中唯一的段寄存器。

- 段重写运算符出现在间接运算符)  (括号内。

- 段重写运算符后面的表达式不是即时操作数或内存操作数。

下面的示例生成 C2422：

```cpp
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```
