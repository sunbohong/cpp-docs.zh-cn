---
description: 了解更多：编译器错误 C2728
title: 编译器错误 C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 7ef24dd037f8d765c072a61320da64411248dbc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245299"
---
# <a name="compiler-error-c2728"></a>编译器错误 C2728

“type”：本机数组不能包含此类型

数组创建语法用于创建托管对象或 WinRT 对象的数组。 不能使用本机数组语法创建托管对象或 WinRT 对象的数组。

有关详细信息，请参阅 [数组](../../extensions/arrays-cpp-component-extensions.md)。

以下示例将生成 C2728，并演示如何修复此错误：

```cpp
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
