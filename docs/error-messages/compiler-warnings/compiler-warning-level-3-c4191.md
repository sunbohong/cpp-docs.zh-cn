---
description: 详细了解：编译器警告 (等级 3) C4191
title: 编译器警告（等级 3）C4191
ms.date: 11/04/2016
f1_keywords:
- C4191
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
ms.openlocfilehash: 0a34147a8cdba7e21af706711e5aa433939188ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344232"
---
# <a name="compiler-warning-level-3-c4191"></a>编译器警告（等级 3）C4191

“operator/operation”：从“type of expression”到“type required”的不安全转换

涉及函数指针的几个操作被视为不安全：

- 具有不同调用约定的函数类型。

- 具有不同返回约定的函数类型。

- 具有不同的大小、类型类别或分类的参数或返回类型。

- **`__cdecl`** 仅在从较长的列表转换为较短的列表时 (上的参数列表长度不同，即使较短的是 varargs) 。

- 指向数据的指针 (除了 **`void`** <strong>\*</strong>) 化名为指向函数的指针。

- 将在上产生错误或警告的任何其他类型差异 **`reinterpret_cast`** 。

通过结果指针调用此函数可能会导致程序故障。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

以下示例生成 C4191：

```cpp
// C4191.cpp
// compile with: /W3 /clr
#pragma warning(default: 4191)

void __clrcall f1() { }
void __cdecl   f2() { }

typedef void (__clrcall * fnptr1)();
typedef void (__cdecl   * fnptr2)();

int main() {
   fnptr1 fp1 = static_cast<fnptr1>(&f1);
   fnptr2 fp2 = (fnptr2) &f2;

   fnptr1 fp3 = (fnptr1) &f2;   // C4191
   fnptr2 fp4 = (fnptr2) &f1;   // C4191
};
```
