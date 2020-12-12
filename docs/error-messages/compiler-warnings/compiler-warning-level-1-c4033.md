---
description: 了解详细信息：编译器警告 (等级 1) C4033
title: 编译器警告（等级 1）C4033
ms.date: 11/04/2016
f1_keywords:
- C4033
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
ms.openlocfilehash: 1d2455d62b3c375b0f1a863e6cfc3064f44e840a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325954"
---
# <a name="compiler-warning-level-1-c4033"></a>编译器警告（等级 1）C4033

“function”必须返回值

此函数未返回值。 返回了一个未定义的值。

使用 **`return`** 不带返回值的函数必须声明为类型 **`void`** 。

此错误针对 C 语言代码。

以下示例生成 C4033：

```c
// C4033.c
// compile with: /W1 /LD
int test_1(int x)   // C4033 expected
{
   if (x)
   {
      return;   // C4033
   }
}
```
