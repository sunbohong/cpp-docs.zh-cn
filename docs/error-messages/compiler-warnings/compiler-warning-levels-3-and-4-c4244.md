---
description: 了解详细信息：编译器警告 (等级3和 4) C4244
title: 编译器警告（等级 3 和等级 4）C4244
ms.date: 11/04/2016
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
ms.openlocfilehash: 60c23dde99a74dd47d2a01d60ac97d1214dc13d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285144"
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>编译器警告（等级 3 和等级 4）C4244

从“type1”到“type2”的“conversion”转换，可能丢失数据

整数类型转换为更小的整数类型。 如果 *type1* 为 **`int`** ，并且 *type2* 小于，则这是一个级别4警告 **`int`** 。 否则为级别 3 (向类型) 的变量分配 [__int64](../../cpp/int8-int16-int32-int64.md) 类型的值 **`unsigned int`** 。 可能发生了数据丢失。

如果收到 C4244，则应将程序更改为使用兼容类型，或向代码添加一些逻辑，以确保可能值的范围将始终与你使用的类型兼容。

C4244 也可以在第2级激发;有关详细信息，请参阅 [编译器警告 (等级 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) 。

该转换可能会因隐式转换而出现问题。

下面的示例生成 C4244：

```cpp
// C4244_level4.cpp
// compile with: /W4
int aa;
unsigned short bb;
int main() {
   int b = 0, c = 0;
   short a = b + c;   // C4244

   bb += c;   // C4244
   bb = bb + c;   // C4244
   bb += (unsigned short)aa;   // C4244
   bb = bb + (unsigned short)aa;   // OK
}
```

有关详细信息，请参阅 [常用算术转换](../../c-language/usual-arithmetic-conversions.md)。

```cpp
// C4244_level3.cpp
// compile with: /W3
int main() {
   __int64 i = 8;
   unsigned int ii = i;   // C4244
}
```

如果为 64 位目标生成的代码在为 32 位目标进行生成时不生成警告，则会出现警告 C4244。 例如，指针之间的一个区别是，在 32 位平台上为 32 位数量，但在 64 位平台上则为 64 位数量。

下面的示例在为 64 位目标进行编译时生成 C4244：

```cpp
// C4244_level3_b.cpp
// compile with: /W3
int main() {
   char* p1 = 0;
   char* p2 = 0;
   int x = p2 - p1;   // C4244
}
```
