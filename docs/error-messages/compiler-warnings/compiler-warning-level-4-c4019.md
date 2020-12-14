---
description: 详细了解：编译器警告 (级别 4) C4019
title: 编译器警告（等级 4）C4019
ms.date: 11/04/2016
f1_keywords:
- C4019
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
ms.openlocfilehash: 0a8d8524cda43f4e30b566e0c9133580b1f0b6c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262173"
---
# <a name="compiler-warning-level-4-c4019"></a>编译器警告（等级 4）C4019

全局范围内的空语句

全局范围内的分号前面没有语句。

如果删除额外的分号，则可能会修复此警告。

## <a name="example"></a>示例

```c
// C4019.c
// compile with: /Za /W4
#define declint( varname ) int varname;
declint( a );   // C4019, int a;;
declint( b )   // OK, int b;

int main()
{
}
```
