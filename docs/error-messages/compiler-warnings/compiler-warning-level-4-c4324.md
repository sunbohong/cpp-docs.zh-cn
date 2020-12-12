---
description: 详细了解：编译器警告 (级别 4) C4324
title: 编译器警告（等级 4）C4324
ms.date: 11/04/2016
f1_keywords:
- C4324
helpviewer_keywords:
- C4324
ms.assetid: 420fa929-d9c0-40b4-8808-2d8ad3ca8090
ms.openlocfilehash: 96554085fa63f4a4f91b954c1f32960b19f1dc6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294543"
---
# <a name="compiler-warning-level-4-c4324"></a>编译器警告（等级 4）C4324

"struct_name"：结构已填充，因为 __declspec (对齐 ( # A2 # A3

已将填充添加到结构的末尾，因为指定了 [__declspec (对齐) ](../../cpp/align-cpp.md) 值。

例如，下面的代码生成 C4324：

```cpp
// C4324.cpp
// compile with: /W4
struct __declspec(align(32)) A
{
   char a;
};   // C4324

int main()
{
}
```
