---
description: 了解更多：编译器错误 C2191
title: 编译器错误 C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: b3b2133e70eeae566a972b0e5db11105b316d6f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337666"
---
# <a name="compiler-error-c2191"></a>编译器错误 C2191

第二个参数列表比第一个长

第二次用更长的参数列表声明了 C 函数。 C 不支持重载函数。

## <a name="example"></a>示例

下面的示例生成 C2191：

```c
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```
