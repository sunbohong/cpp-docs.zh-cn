---
description: 详细了解：编译器警告 (级别 4) C4032
title: 编译器警告 (等级 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 1c150bff398bbd2d6e5f1a8d21211f4c6b4cb6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262095"
---
# <a name="compiler-warning-level-4-c4032"></a>编译器警告 (等级 4) C4032

提升时形参 "number" 的类型不同

通过默认升级，参数类型与以前声明中的类型不兼容。

这是 ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中的错误和 Microsoft 扩展 (/ze) 下的警告。

## <a name="example"></a>示例

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```
