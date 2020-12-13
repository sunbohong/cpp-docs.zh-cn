---
description: 详细了解：编译器警告 (级别 4) C4255
title: 编译器警告（等级 4）C4255
ms.date: 11/04/2016
f1_keywords:
- C4255
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
ms.openlocfilehash: 31c5a121c944a65a0a5c3cd13d3e6201c3ad43a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339161"
---
# <a name="compiler-warning-level-4-c4255"></a>编译器警告（等级 4）C4255

"function"：未给出函数原型：将 " ( # A1" 转换为 " (void) "

编译器未找到函数的自变量的显式列表。 此警告仅适用于 C 编译器。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4255：

```c
// C4255.c
// compile with: /W4 /WX
#pragma warning (default : 4255)

void f()  { // C4255
// try the following line instead
//void f(void) {
}

int main(int argc, char *argv[]) {
   f();
}
```
