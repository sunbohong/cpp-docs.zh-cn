---
description: 了解更多：编译器错误 C2821
title: 编译器错误 C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: c21c9dc0b1413292e1d73b6448ed008d6fc9a64d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194691"
---
# <a name="compiler-error-c2821"></a>编译器错误 C2821

"operator new" 的第一个形参必须是 "无符号 int"

[运算符 new](../../standard-library/new-operators.md#op_new)的第一个形参必须是无符号 **`int`** 。

## <a name="example"></a>示例

下面的示例生成 C2821：

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```
